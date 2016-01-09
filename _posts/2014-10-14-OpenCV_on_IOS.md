---     
layout: post     
title:  "OpenCV_on_IOS"     
date:   2014-10-14 06:18:00     
categories: IOS     
---     


实话说，在对openCV一点不了解的情况下，直接搞ios版是走了很多弯路的。而且网上的教程都已经过时，新版的xcode用起来方便了很多。     

赶紧记录下正确路线：     

1. 下载openCV的IOS库：**[我是链接](http://opencv.org/downloads.html)**     
2. 下载得到的库直接拖到项目里面去即可（记得勾选`add to target`）     
3. 所有用到C++库的**`.m`**文件，改成**`.mm`**以支持编译C++语法     
4. C++语法和OC语法混合后比较诡异，可以在**`.mm`**中**`using name space`**但是不可以定义全局函数。定义的“分类”也需要手动添加头文件。     

这样，openCV就算引入到xcode中了。（凡未提到的步骤一律不要，亲测！）     

最后，补充一下Mat与UIImage之间的转换代码，摘自官网：**[我是链接](http://docs.opencv.org/doc/tutorials/ios/image_manipulation/image_manipulation.html#opencviosimagemanipulation)：**     

{% highlight Objective-c linenos %}     

//这个是UIImage转Mat     
- (cv::Mat)cvMatFromUIImage:(UIImage *)image     
{     
  CGColorSpaceRef colorSpace = CGImageGetColorSpace(image.CGImage);     
  CGFloat cols = image.size.width;     
  CGFloat rows = image.size.height;     

  cv::Mat cvMat(rows, cols, CV_8UC4); // 8 bits per component, 4 channels (color channels + alpha)     

  CGContextRef contextRef = CGBitmapContextCreate(cvMat.data,                 // Pointer to  data     
                                                 cols,                       // Width of bitmap     
                                                 rows,                       // Height of bitmap     
                                                 8,                          // Bits per component     
                                                 cvMat.step[0],              // Bytes per row     
                                                 colorSpace,                 // Colorspace     
                                                 kCGImageAlphaNoneSkipLast |     
                                                 kCGBitmapByteOrderDefault); // Bitmap info flags     

  CGContextDrawImage(contextRef, CGRectMake(0, 0, cols, rows), image.CGImage);     
  CGContextRelease(contextRef);     

  return cvMat;     
}     




//这个是Mat转回UIImage     
-(UIImage *)UIImageFromCVMat:(cv::Mat)cvMat     
{     
    NSData *data = [NSData dataWithBytes:cvMat.data length:cvMat.elemSize()*cvMat.total()];     
    CGColorSpaceRef colorSpace;     
    
    if (cvMat.elemSize() == 1) {     
        colorSpace = CGColorSpaceCreateDeviceGray();     
    } else {     
        colorSpace = CGColorSpaceCreateDeviceRGB();     
    }     
    
    CGDataProviderRef provider = CGDataProviderCreateWithCFData((__bridge CFDataRef)data);     
    
    // Creating CGImage from cv::Mat     
    CGImageRef imageRef = CGImageCreate(cvMat.cols,                                 //width     
                                        cvMat.rows,                                 //height     
                                        8,                                          //bits per component     
                                        8 * cvMat.elemSize(),                       //bits per pixel     
                                        cvMat.step[0],                            //bytesPerRow     
                                        colorSpace,                                 //colorspace     
                                        kCGImageAlphaNone|kCGBitmapByteOrderDefault,// bitmap info     
                                        provider,                                   //CGDataProviderRef     
                                        NULL,                                       //decode     
                                        false,                                      //should interpolate     
                                        kCGRenderingIntentDefault                   //intent     
                                        );     
    
    
    // Getting UIImage from CGImage     
    UIImage *finalImage = [UIImage imageWithCGImage:imageRef];     
    CGImageRelease(imageRef);     
    CGDataProviderRelease(provider);     
    CGColorSpaceRelease(colorSpace);     
    
    return finalImage;     
}     

{% endhighlight %}     


最后，附上我折腾一晚上的，我的第一个ios应用，**[GitHub](https://github.com/rulerstorm/HelloOpenCV)**     


