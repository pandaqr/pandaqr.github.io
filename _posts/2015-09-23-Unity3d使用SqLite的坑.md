---     
layout: post     
title:  "Unity3d使用SqLite的坑"     
date:   2015-09-23 06:19     
categories: TOOLS     
---     

SqLite作为轻量级C语言本地数据库，一直是挺讨我喜欢。这次实验室的Unity项目需要本地数据库，就研究了下怎么在Unity3D中集成sqlite。想不到坑那么多，各种坑，也是醉了。     

步骤如下：     
1. Create new folder under Assets Folder Rename it `Plugins`.     
2. Copy `sqlite3.def` and sqlite3.dll into `Assets/Plugins` in your unity project .You can download these files here `http://www.sqlite.org/download.html` for windows (Precompiled Binaries for Windows)     
3. Download SQLite Browser `https://github.com/sqlitebrowser/sqlitebrowser`（GUI数据库编辑器）     
4. Create Database in `Assets` folder in your unity project using SQLite Browser.（必须先手动创建好）     
5. Copy `System.Data.dll` and `Mono.Data.Sqlite.dll` from `C:\Program Files (x86)\Unity \Editor\Data\Mono\lib\mono\2.0*` and paste them in your `Assets/Plugins*` folder in your unity project.     
6. Add these namespaces `using Mono.Data.Sqlite; using System.Data; using System;`     

然后，可以写一个helper类，unity里面可以自动引用。核心代码如下：     

```C#     
        string dbName =  "/testDatabase.db";   //注意这里很容易出错，小心别漏了/号     
        string tableName = "testTable";     
        
        //开始建立连接     
        string conn = "URI=file:" + Application.dataPath + dbName; //Path to database.         IDbConnection dbconn;     
        dbconn = (IDbConnection)new SqliteConnection(conn);     
        dbconn.Open(); //Open connection to the database.     

        //准备查询语句     
        IDbCommand dbcmd = dbconn.CreateCommand();     
        string sqlQuery = "SELECT * FROM " + tableName;     
        dbcmd.CommandText = sqlQuery;     
        //执行语句     
        IDataReader reader = dbcmd.ExecuteReader();     
        
    
        //下面开始处理返回数据     
        while (reader.Read())     
        {     
            int ID = reader.GetInt32(0);      //返回一个数组，下标0则第一个字段     
            string text = reader.GetString(1) + '\n';   //第二个字段     
            Debug.Log("ID= " + ID + "  name =" + name);     
        }     
  
        //下面开始关闭连接     
        reader.Close();     
        reader = null;     
        dbcmd.Dispose();     
        dbcmd = null;     
        dbconn.Close();     
        dbconn = null;     
```     

##### 坑在哪里？     
这样子在编辑器里面就OK了，可是！不能编译。。。醉了，查了一下，需要调整Unity项目的设置，如下：     
`PlayerSetting -> Other Settings -> Optimization -> Api Compatibility Level`这个下拉菜单，手动选择为：`.NET 2.0`。     
于是我们终于可以编译了。     

##### 别高兴太早，编译好之后的程序访问不了数据库。。。。     
经过长时间的反复排查，最后打印了db的路径，终于发现。。。编译的时候没有把数据库复制过去。。。需要`手动`把数据库复制到各个平台的运行文件中。     
具体路径可打印`Application.dataPath`获得。     


真不容易。。。     
