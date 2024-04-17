import javax.swing.table.*;
import java.sql.*;
import java.awt.event.*;
import java.awt.*;
import javax.swing.*;
public class slip10 extends JFrame implements ActionListener
{
JTextField t1,t2,t3;
JLabel l1,l2,l3;
Connection con=null;
JButton b2;
int row,column;
slip10()
{

setLayout(new FlowLayout());
etSize(500,500);
setVisible(true);
setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

l1=new JLabel("RollNo");
add(l1);

t1=new JTextField(10);
add(t1);
l2=new JLabel("Name");
add(l2);

t2=new JTextField(10);
add(t2);

l3=new JLabel("Percentage");
add(l3);

t3=new JTextField(10);
add(t3);



b2=new JButton("Display FIRST RECORD");
add(b2);
b2.addActionListener(this);

try
{
Class.forName("org.postgresql.Driver");
con=DriverManager.getConnection("jdbc:postgresql://localhost/ty51","postgres","");
}
catch(Exception e)
{
System.out.println("Error"+e.getMessage());
}
}


public void actionPerformed(ActionEvent e2)
{

if(e2.getSource()==b2)
{
try
{
ResultSet rs=null;
Statement st=con.createStatement(rs.TYPE_SCROLL_SENSITIVE,rs.CONCUR_READ_ONLY);

rs=st.executeQuery("select * from student");
rs.first();
t1.setText(Integer.toString(rs.getInt(1)));
t2.setText(rs.getString(2));
t3.setText(Integer.toString(rs.getInt(3)));
}catch(Exception e)
{
System.out.println("Error"+e.getMessage());
}

}

}


public static void main(String[] args) throws Exception
{
new slip10();
}
}

