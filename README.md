
#### 登陆MySQL数据库，以及几个简单操作

- 登陆mysql

打cmd命令终端，如果已经添加了mysql的环境变量，可以直接使用命令

mysql -uroot 

直接回车，之后按提示输入密码，

如果未添加mysql的环境变量，可以切换到mysql的安装目录下的bin目录，再使用

mysq -uroot

你也可以手动为mysql添加环境变量。这里就不介绍怎么添加环境变量的方法了

密码输入正确之后，就会出现“Welcome to the MySQL monitor.  Commands end with ; or \g. ......”字样，

命令行出现“mysql>”字符前缀。现在你就可以使用命令对mysql进行操作了。曾经有没有过这样的经历，原来看见别人在命令行里面咔咔的猛敲时，就一通的崇拜，觉得这人很牛，现在你也可以让别一通崇拜了。

mysql的所有命令都以";"或者\g为结束符

- 查看MySQL服务所在的端口号

show global variables like 'port';  

- 查看MySQL版本

status;  或者  show global variables like 'port';  


- 新建数据库

在新建数据库之后，我们先设置一下字符集

mysql>SET NAMES utf8;

然后再创建数据库

mysql>CREATE DATABASE lesson

- 显示所有数据库

mysql>SHOW DATABASES;

- 使用数据库
 
 mysql>USE 数据库名;

- 新建表

mysql>CREATE TABLE study(

   id int(11) unsigned NOT NULL AUTO_INCREMENT COMMENT '学生id号',

   username varchar(30) NOT NULL DEFAULT '' COMMENT '学生名字',

  class tinyint(3) unsigned NOT NULL,

  sex enum('男','女','保密')  CHARACTER SET utf8 COLLATE utf8_general_ci NOT NULL DEFAULT '保密' COMMENT '性别',

  addtime int(10) NOT NULL DEFAULT '0',

   PRIMARY KEY (id)

)ENGINE=InnoDB  COMMENT = '学生表';

- 显示所有表

mysql>SHOW TABLES;

- 修改表的名称 

mysql>RENAME TABLE study TO study_new ;

或者

mysql>ALTER TABLE study_new RENAME TO study;

- 显示字段信息

 SHOW COLUMNS FROM study或者DESCRIBE study



- 插入数据

mysql> insert into study (username,class,sex)VALUES('小王',1,'男'),('小四',2,'女');





- 查询数据（使concat函数拼接数据）

mysql> SELECT username,CONCAT(class,'班'),sex FROM study;

- 删除数据

mysql>DELETE FROM study WHERE  id=1;

- 删除数据表

DROP TABLE study;

- 删除数据库

mysql> DROP DATABASE lesson;


#### JDBC链接本地MySQL数据库，创建表结构并添加数据和查询数据



···java

import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Connection;
import java.sql.Statement;

public class Main {

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


