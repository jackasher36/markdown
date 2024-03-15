把JDBC封装在一个类，可以直接完成加载连接关闭

```java
package com.example.oa;

import java.sql.*;
import java.util.ResourceBundle;

public class DBUil {
    private static ResourceBundle bundle = ResourceBundle.getBundle("resources.jdbc");
    private static String driver = bundle.getString("driver");
    private static String url = bundle.getString("url");
    private static String user = bundle.getString("user");
    private static String password = bundle.getString("password");
    static {
        try {
            Class.forName(driver);
        } catch (ClassNotFoundException e) {
            throw new RuntimeException(e);
        }
    }
    public static Connection getConnection (String[] args) throws SQLException {
        Connection connection = DriverManager.getConnection(url,user,password);
        return connection;
    }
    public static void close(Connection connection, Statement ps, ResultSet rs){
        if (rs != null){
            try {
                rs.close();
            } catch (SQLException e) {
                throw new RuntimeException(e);
            }
        }
        if (ps != null){
            try {
                ps.close();
            } catch (SQLException e) {
                throw new RuntimeException(e);
            }
        }
        if (connection != null){
            try {
                connection.close();
            } catch (SQLException e) {
                throw new RuntimeException(e);
            }
        }
        
       
    
    }
}

```

