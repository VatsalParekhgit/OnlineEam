# OnlineExam
Project on Examination system using JDBC


Q1.java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {
 String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
       String DB_DRV ="com.mysql.jdbc.Driver";
       String DB_USER = "root";
       String DB_PASSWD = "1009";

      Connection connection = null;
      Statement statement = null;
      ResultSet resultSet = null;

      try{
         connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
	statement=connection.createStatement();
        String q;
        q="create table counter(marks int(5));";
        ResultSet rs;
        String qt;
         resultSet=statement.executeQuery
            (q);
     if(jRadioButton2.isSelected()==true)
        {
         
        qt="insert into counter values(1);";
        rs=statement.executeQuery(qt);    
    }
     else
     {
         qt="insert into counter values(0);";
        rs=statement.executeQuery(qt);
     }
      }
     catch(SQLException ex){
      }finally{
          new q2().setVisible(true);
         try {
            resultSet.close();
            statement.close();
            connection.close();
         } catch (SQLException ex) {
			   JOptionPane.showMessageDialog(this, ex);
		} 
	 
          }
          }
          


Q2.java
     private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:

        String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
        String DB_DRV ="com.mysql.jdbc.Driver";
        String DB_USER = "root";
        String DB_PASSWD = "1009";

        Connection connection = null;
        Statement statement = null;
       

        try{
            connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
            statement=connection.createStatement();
            ResultSet rs;
            String qt;
            
            if(jRadioButton4.isSelected()==true)
            {

                qt="update counter set marks=marks+1;";
                rs=statement.executeQuery(qt);

            }
            else
            {
                ;
            }
        }
        catch(SQLException ex){
        }finally{
            new q3().setVisible(true);
            try {
               
                statement.close();
                connection.close();
            } catch (SQLException ex) {
                JOptionPane.showMessageDialog(this, ex);
            }

        }

    }                   
    
    Q3.java
    
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:

        String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
        String DB_DRV ="com.mysql.jdbc.Driver";
        String DB_USER = "root";
        String DB_PASSWD = "1009";

        Connection connection = null;
        Statement statement = null;
       

        try{
            connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
            statement=connection.createStatement();
            ResultSet rs;
            String qt;
            
              if(jRadioButton4.isSelected()==true)
            {

                qt="update counter set marks=marks+1;";
                rs=statement.executeQuery(qt);

            }
            else
            {
                ;
            }
        }
        catch(SQLException ex){
        }finally{
            new q4().setVisible(true);
            try {
                
                statement.close();
                connection.close();
            } catch (SQLException ex) {
                JOptionPane.showMessageDialog(this, ex);
            }

        }
    }                                        

Q4.java

private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:

        String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
        String DB_DRV ="com.mysql.jdbc.Driver";
        String DB_USER = "root";
        String DB_PASSWD = "1009";

     
        Connection connection = null;
        Statement statement = null;
       

        try{
            connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
            statement=connection.createStatement();
            ResultSet rs;
            String qt;
            
              if(jRadioButton3.isSelected()==true)
            {

                qt="update counter set marks=marks+1;";
                rs=statement.executeQuery(qt);

            }
            else
            {
                ;
            }
        }
        catch(SQLException ex){
        }finally{
            new q5().setVisible(true);
            try {
                
                statement.close();
                connection.close();
            } catch (SQLException ex) {
                JOptionPane.showMessageDialog(this, ex);
            }

        }
    }                                        


Q5.java
private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:

        String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
        String DB_DRV ="com.mysql.jdbc.Driver";
        String DB_USER = "root";
        String DB_PASSWD = "1009";

        
        Connection connection = null;
        Statement statement = null;
       

        try{
            connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
            statement=connection.createStatement();
            ResultSet rs;
            String qt;
            
              if(jRadioButton4.isSelected()==true)
            {

                qt="update counter set marks=marks+1;";
                rs=statement.executeQuery(qt);

            }
            else
            {
                ;
            }
        }
        catch(SQLException ex){
        }finally{
            new register().setVisible(true);
            try {
                statement.close();
                connection.close();
            } catch (SQLException ex) {
                JOptionPane.showMessageDialog(this, ex);
            }

        }
    }                    
    
    
    Register.java
    
    private void jButton1ActionPerformed(java.awt.event.ActionEvent evt) {                                         
        // TODO add your handling code here:
        String rollno=jTextField1.getText();
        		
       String DB_URL ="jdbc:mysql://localhost:3306/onlinetest";
       String DB_DRV ="com.mysql.jdbc.Driver";
       String DB_USER = "root";
       String DB_PASSWD = "1009";

      Connection connection = null;
      Statement statement = null;
      ResultSet resultSet = null;

      try{
         connection=DriverManager.getConnection
            (DB_URL,DB_USER,DB_PASSWD);
	statement=connection.createStatement();
        String q;
        q="SELECT count(Enroll) FROM student where Enroll="+rollno;
        ResultSet rs,ds;
        String qt,dt;
         resultSet=statement.executeQuery(q);
         int counter = 0;
    while(resultSet.next())
    {
    counter++;
    }
    if(counter>1)
        {
           JOptionPane.showMessageDialog(this, "Your Record is already Present");
        }
    else
    {
        qt="insert into student (Enroll,marks)'"+rollno+"',select marks from counter;";
        rs=statement.executeQuery(qt);
        dt="drop table counter;";
        ds=statement.executeQuery(dt);
        ResultSet results = statement.executeQuery("SELECT * FROM student where Enroll="+rollno+";");
        String ed;int md;
        ed=results.getString(1);
        md=results.getInt(1);
 JOptionPane.showMessageDialog(this, "Student Enrollment Numbeer "+ed+" scored= "+md);
 
    }
      }
     catch(SQLException ex){
      }finally{
         try {
            resultSet.close();
            statement.close();
            connection.close();
         } catch (SQLException ex) {
			   JOptionPane.showMessageDialog(this, ex);
		} 
	 
      }
    }              
        
    
    OnlineTest.sql
    -- MySQL dump 10.13  Distrib 5.5.53, for Win64 (AMD64)
--
-- Host: localhost    Database: onlinetest
-- ------------------------------------------------------
-- Server version	5.5.53

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `student`
--

DROP TABLE IF EXISTS `student`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!40101 SET character_set_client = utf8 */;
CREATE TABLE `student` (
  `Enroll` varchar(30) DEFAULT NULL,
  `marks` int(5) DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=latin1;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `student`
--

LOCK TABLES `student` WRITE;
/*!40000 ALTER TABLE `student` DISABLE KEYS */;
/*!40000 ALTER TABLE `student` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2020-04-30 16:58:23
