
#### 安装MySQL数据库

一、MYSQL的安装

１、打开下载的mysql安装文件mysql-5.0.27-win32.zip，双击解压缩，运行“setup.exe”。

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2761423-da29159920d0782a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 

２、选择安装类型，有“Typical（默认）”、“Complete（完全）”、“Custom（用户自定义）”三个选项，选择“Custom”，按“next”键继续。


![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2761423-1b1c70abf2c01614.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

３、在“Developer
Components（开发者部分）”上左键单击，选择“This feature,

and all
subfeatures, will be installed on local hard drive.”，即“此部分，及下属子部分内容，全部安装在本地硬盘上”。在上面的“MySQL Server（mysql服务器）”、“Client Programs（mysql客户端程序）”、“Documentation（文档）”也如此操作，以保证安装所有文件。点选“Change...”，手动指定安装目录。



![03.png](http://upload-images.jianshu.io/upload_images/2761423-ca60fef9c01c1910.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 

４、填上安装目录，我的是“F:\Server\MySQL\MySQL
Server 5.0”，也建议不要放在与操作系统同一分区，这样可以防止系统备份还原的时候，数据被清空。按“OK”继续。



![04.png](http://upload-images.jianshu.io/upload_images/2761423-d09581e5293dc7aa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

确认一下先前的设置，如果有误，按“Back”返回重做。按“Install”开始安装。



![05.png](http://upload-images.jianshu.io/upload_images/2761423-949139da1478d625.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![06.png](http://upload-images.jianshu.io/upload_images/2761423-d40132757af84aa7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



５、正在安装中，请稍候，直到出现下面的界面


![Paste_Image.png](http://upload-images.jianshu.io/upload_images/2761423-79eb7f624fc38638.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

这里是询问你是否要注册一个mysql.com的账号，或是使用已有的账号登陆mysql.com，一般不需要了，点选“Skip Sign-Up”，按“Next”略过此步骤。继续则完成MYSQL的安装。

 

 
二、MYSQL的配置


１、安装完成了，出现如下界面将进入mysql配置向导。



![08.png](http://upload-images.jianshu.io/upload_images/2761423-d9b7cf24ef9ba0fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![09.png](http://upload-images.jianshu.io/upload_images/2761423-bc345e30530c5a15.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 

２、选择配置方式，“Detailed
Configuration（手动精确配置）”、“Standard Configuration（标准配置）”，我们选择“Detailed Configuration”，方便熟悉配置过程。 


![10.png](http://upload-images.jianshu.io/upload_images/2761423-a36214598f3d0c5c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

３、选择服务器类型，“Developer
Machine（开发测试类，mysql占用很少资源）”、“Server Machine（服务器类型，mysql占用较多资源）”、“Dedicated MySQL Server Machine（专门的数据库服务器，mysql占用所有可用资源）”

 

![10.png](http://upload-images.jianshu.io/upload_images/2761423-059f8c75d4da330e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 

４、选择mysql数据库的大致用途，“Multifunctional
Database（通用多功能型，好）”、“Transactional
Database Only（服务器类型，专注于事务处理，一般）”、“Non-Transactional Database Only（非事务处理型，较简单，主要做一些监控、记数用，对MyISAM数据类型的支持仅限于non-transactional），按“Next”继续。


![11.png](http://upload-images.jianshu.io/upload_images/2761423-eb586bcfcf17261b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

５、选择网站并发连接数，同时连接的数目，“Decision
Support(DSS)/OLAP（20个左右）”、“Online Transaction Processing(OLTP)（500个左右）”、“Manual Setting（手动设置，自己输一个数）”。

![12.png](http://upload-images.jianshu.io/upload_images/2761423-57b941762f5958cc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

６、是否启用TCP/IP连接，设定端口，如果不启用，就只能在自己的机器上访问mysql数据库了，在这个页面上，您还可以选择“启用标准模式”（Enable Strict Mode），这样MySQL就不会允许细小的语法错误。如果是新手，建议您取消标准模式以减少麻烦。但熟悉MySQL以后，尽量使用标准模式，因为它可以降低有害数据进入数据库的可能性。按“Next”继续


![13.png](http://upload-images.jianshu.io/upload_images/2761423-e93955381528b1d9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

７、就是对mysql默认数据库语言编码进行设置（重要），一般选UTF-8，按“Next”继续。



![14.png](http://upload-images.jianshu.io/upload_images/2761423-26c2f83468263f7b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

８、选择是否将mysql安装为windows服务，还可以指定Service
Name（服务标识名称），是否将mysql的bin目录加入到Windows
PATH（加入后，就可以直接使用bin下的文件，而不用指出目录名，比如连接，“mysql.exe
-uusername -ppassword;”就可以了，不用指出mysql.exe的完整地址，很方便），我这里全部打上了勾，Service
Name不变。按“Next”继续。



![15.png](http://upload-images.jianshu.io/upload_images/2761423-c3161c7b7ff13193.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

９、询问是否要修改默认root用户（超级管理）的密码。“Enable root access from
remote machines（是否允许root用户在其它的机器上登陆，如果要安全，就不要勾上，如果要方便，就勾上它）”。最后“Create An Anonymous Account（新建一个匿名用户，匿名用户可以连接数据库，不能操作数据，包括查询）”，一般就不用勾了，设置完毕，按“Next”继续。


![16.png](http://upload-images.jianshu.io/upload_images/2761423-66fad2794b80cc68.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

 
１０、确认设置无误，按“Execute”使设置生效，即完成MYSQL的安装和配置。



![17.png](http://upload-images.jianshu.io/upload_images/2761423-abd1831cf8f7b064.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![18.png](http://upload-images.jianshu.io/upload_images/2761423-e8a8937fdf6c89fa.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
 

**注意**：设置完毕，按“Finish”后有一个比较常见的错误，就是不能“Start
service”，一般出现在以前有安装mysql的服务器上，解决的办法，先保证以前安装的mysql服务器彻底卸载掉了；不行的话，检查是否按上面一步所说，
之前的密码是否有修改，照上面的操作；如果依然不行，将mysql安装目录下的data文件夹备份，然后删除，在安装完成后，将安装生成的data文件夹删除，
备份的data文件夹移回来，再重启mysql服务就可以了，这种情况下，可能需要将数据库检查一下，然后修复一次，防止数据出错。

#### 登陆MySQL数据库，以及常用操作命令

- 登陆mysql


打cmd命令终端，如果已经添加了mysql的环境变量，可以直接使用命令
```sql
mysql -uroot -p
```
直接回车，之后按提示输入密码，

如果未添加mysql的环境变量，可以切换到mysql的安装目录下的bin目录，再使用
```sql
mysq -uroot
```
你也可以手动为mysql添加环境变量。这里就不介绍怎么添加环境变量的方法了

密码输入正确之后，就会出现“Welcome to the MySQL monitor.  Commands end with ; or \g. ......”字样，

命令行出现“mysql>”字符前缀。现在你就可以使用命令对mysql进行操作了。曾经有没有过这样的经历，原来看见别人在命令行里面咔咔的猛敲时，就一通的崇拜，觉得这人很牛，现在你也可以让别一通崇拜了。

mysql的所有命令都以";"或者\g为结束符

- 查看MySQL服务所在的端口号
```sql
show global variables like 'port';  
```
- 查看MySQL版本
```sql
status;  或者  show global variables like 'port';  
```

- 新建数据库

在新建数据库之后，我们先设置一下字符集
```sql
SET NAMES utf8;
```
然后再创建数据库
```sql
CREATE DATABASE lesson
```
- 显示所有数据库
```sql
SHOW DATABASES;
```
- 使用数据库
```sql
USE 数据库名;
```
- 新建表
```sql
CREATE TABLE study(
id int(11) unsigned NOT NULL AUTO_INCREMENT COMMENT '学生id号',
username varchar(30) NOT NULL DEFAULT 'xiaoming' COMMENT '学生名字',
class tinyint(3) unsigned NOT NULL,
sex enum('男','女','保密') CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL DEFAULT '保密' COMMENT '性别',
addtime int(10) NOT NULL DEFAULT '0',
PRIMARY KEY (id)
)ENGINE=InnoDB COMMENT = '学生表';
```
- 显示所有表
```sql
SHOW TABLES;
```
- 修改表的名称 
```sql
RENAME TABLE study TO study_new ;
```
或者
```sql
ALTER TABLE study_new RENAME TO study;
```
- 显示字段信息
```sql
 SHOW COLUMNS FROM study或者DESCRIBE study
```
- 插入数据
```sql
insert into study (username,class,sex)VALUES('小王',1,'男'),('小四',2,'女');
```

- 查询数据（使concat函数拼接数据）
```sql
SELECT username,CONCAT(class,'班'),sex FROM study;
```
- 删除数据
```sql
DELETE FROM study WHERE  id=1;
```
- 删除数据表
```sql
DROP TABLE study;
```
- 删除数据库
```sql
DROP DATABASE lesson;

####Cmd命令行窗口中,MySQL表中数据乱码问题

百度了一下。。有说将cmd字符编码用chcp命令改为65001（utf8字符编码），可这样之后根本无法输入中文，查询出的中问结果依旧乱码 
其实，只要保证cmd客户端和MySQL两者编码一致即可。 
但现实是cmd默认的是gbk（cmd属性可以看到中文操作系统下面是gbk编码），而mysql一般是utf8（我的也是），之前一直进入误区，想要更改cmd的字符编码，可是并不能行得通。网友中提到在mysql中关于客户端编码问题，只需在cmd里告诉mysql服务器我客户端这边编码和想要的结果集编码即可。

具体步骤：
1、win+r进入cmd，然后切到mysql安装目录的bin文件夹下（或者直接打开我的电脑找到bin文件夹，在上方地址栏输入cmd）；

2、输入 mysql -uroot -p，然后按提示输入密码计入数据库；

3、设置编码；

>此时输入 set character_set_client=gbk;告诉我客户端这边的文字编码
再输入set character_set_results=gbk; 告诉mysql希望返回的结果集编码；实验中发现只要客户端是gbk编码的，只要设置这个就可以解决乱码这个问题。

还有另外一个好用的命令可以同时达到上面两条指令的效果：

>set charset gbk;//和上面两个效果一致。

大功告成！去插入中文字段试试吧！
```
#### JDBC链接本地MySQL数据库，创建表结构并添加数据和查询数据

首先我们要下载JDBC的jar包，本项目中jar放在了lib目录中，大家可以直接使用我这个mysql-connector-java-5.1.42-bin.jar包。

然后添加一个Main,使用JDBC链接MySQL数据库，创建表结构并添加数据和查询数据

具体代码：


```java
public class Main{

    public static void main(String[] args) throws Exception {
        connectMySQLTest01();
        connectMySQLTest02();
        connectMySQLTest03();
    }

    //链接数据库，创建student表，并添加内容
    private static void connectMySQLTest01() throws SQLException {
        Connection conn = null;
        String sql;
        // MySQL的JDBC URL编写方式：jdbc:mysql://主机名称：连接端口/数据库的名称?参数=值
        // 避免中文乱码要指定useUnicode和characterEncoding
        // 执行数据库操作之前要在数据库管理系统上创建一个数据库，名字自己定，
        // 下面语句之前就要先创建javademo数据库
        String url = "jdbc:mysql://localhost:3306/test?"
                + "user=root&password=123456&useUnicode=true&characterEncoding=UTF8";

        try {
            // 之所以要使用下面这条语句，是因为要使用MySQL的驱动，所以我们要把它驱动起来，
            // 可以通过Class.forName把它加载进去，也可以通过初始化来驱动起来，下面三种形式都可以
            Class.forName("com.mysql.jdbc.Driver");// 动态加载mysql驱动
            // or:
            // com.mysql.jdbc.Driver driver = new com.mysql.jdbc.Driver();
            // or：
            // new com.mysql.jdbc.Driver();

            System.out.println("成功加载MySQL驱动程序");
            // 一个Connection代表一个数据库连接
            conn = DriverManager.getConnection(url);
            // Statement里面带有很多方法，比如executeUpdate可以实现插入，更新和删除等
            Statement stmt = conn.createStatement();
            sql = "create table student(NO char(20),name varchar(20),primary key(NO))";
            int result = stmt.executeUpdate(sql);// executeUpdate语句会返回一个受影响的行数，如果返回-1就没有成功
            if (result != -1) {
                System.out.println("创建数据表成功");
                sql = "insert into student(NO,name) values('2012001','陶伟基')";
                result = stmt.executeUpdate(sql);
                sql = "insert into student(NO,name) values('2012002','周小俊')";
                result = stmt.executeUpdate(sql);
                sql = "select * from student";
                ResultSet rs = stmt.executeQuery(sql);// executeQuery会返回结果的集合，否则返回空值
                System.out.println("学号\t姓名");
                while (rs.next()) {
                    System.out
                            .println(rs.getString(1) + "\t" + rs.getString(2));// 入如果返回的是int类型可以用getInt()
                }
            }
        } catch (SQLException e) {
            System.out.println("MySQL操作错误");
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            conn.close();
        }
    }

    //链接数据库，查询数据库student表结构的内容
    private static void connectMySQLTest02() throws SQLException {
        Connection conn = null;
        String sql;
        // MySQL的JDBC URL编写方式：jdbc:mysql://主机名称：连接端口/数据库的名称?参数=值
        // 避免中文乱码要指定useUnicode和characterEncoding
        // 执行数据库操作之前要在数据库管理系统上创建一个数据库，名字自己定，
        // 下面语句之前就要先创建javademo数据库
        String url = "jdbc:mysql://localhost:3306/test?"
                + "user=root&password=123456&useUnicode=true&characterEncoding=UTF8";

        try {
            // 之所以要使用下面这条语句，是因为要使用MySQL的驱动，所以我们要把它驱动起来，
            // 可以通过Class.forName把它加载进去，也可以通过初始化来驱动起来，下面三种形式都可以
            Class.forName("com.mysql.jdbc.Driver");// 动态加载mysql驱动
            // or:
            // com.mysql.jdbc.Driver driver = new com.mysql.jdbc.Driver();
            // or：
            // new com.mysql.jdbc.Driver();

            System.out.println("成功加载MySQL驱动程序");
            // 一个Connection代表一个数据库连接
            conn = DriverManager.getConnection(url);
            // Statement里面带有很多方法，比如executeUpdate可以实现插入，更新和删除等
            Statement stmt = conn.createStatement();
            sql = "create table student(NO char(20),name varchar(20),primary key(NO))";
            //查询数据库student表结构数据
            sql = "select * from student";
            ResultSet rs = stmt.executeQuery(sql);// executeQuery会返回结果的集合，否则返回空值
            System.out.println("学号\t姓名");
            while (rs.next()) {
                System.out
                        .println(rs.getString(1) + "\t" + rs.getString(2));// 入如果返回的是int类型可以用getInt()
            }
        } catch (SQLException e) {
            System.out.println("MySQL操作错误");
            e.printStackTrace();
        } catch (Exception e) {
            e.printStackTrace();
        } finally {
            conn.close();
        }
    }

    //封装一个DBHelper类来打开和关闭数据库
    private static void connectMySQLTest03() {

        String sql = "select * from student";//SQL语句
        DBHelper db1 = new DBHelper(sql);//创建DBHelper对象

        try {
            ResultSet ret = db1.pst.executeQuery();//执行语句，得到结果集
            while (ret.next()) {
                System.out
                        .println(ret.getString(1) + "\t" + ret.getString(2));// 入如果返回的是int类型可以用getInt()
            }
            ret.close();
            db1.close();//关闭连接
        } catch (SQLException e) {
            e.printStackTrace();
        }
    }
}

```


项目地址：[传送门](https://github.com/AFinalStone/MySQL)

