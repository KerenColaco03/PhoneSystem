# PhoneSystem

Customer---Editme
Code for Customer login, register, and profile page. (Sample)
How to start Create an empty ASP.NET website.
Add a web form to your project. Design the ASP.NET Registration form.
FirstName. Then add a Textbox beside it LastName Then add a Textbox beside it Email. Then add a Textbox beside it Phone Number. Then add a Textbox beside it Password Then add a Textbox beside it
Add a button and name it REGISTER/SIGN UP Then add a label below.
Add a SQL Server database and create a table.
Step 1: Hit the Control+Shift+A shortcut and select SQL Server Database option. This will prompt you to create an App_Data folder within your project, accept it and open Server Explorer box. Now, you have added a database to your ASP.NET website.
Step 2: From the Server Explorer, right click on the Tables and select the Add New Table option, as shown in the screenshot below.
Name the table RegistrationTable CUST_NO INT (PRIMARY KEY) UNIQUE (SET AS AUTOMATIC) FIRSTNAME VAR (50) LASTNAME VAR (50) PHONE NUMBER. VAR (50) EMAIL. BIGINT (50) PASSWORD BIGINT (50)
FINISH
THEN MOVE TO
Open Web.config file from the Solution Explorer and paste the connection string of your database in the following format within the tags. Do not add the tag inside any other tag.
To get the connectionString of your database, open Server Explorer and right click on it. Select the Properties option. Now, from the Properties box, copy the Connection String of your database and paste it at the specified place in the code snippet.
using System; using System.Collections.Generic; using System.Linq; using System.Web; using System.Web.UI; using System.Web.UI.WebControls; using System.Data; using System.Data.SqlClient; using System.Configuration;
public partial class _Default : System.Web.UI.Page { protected void Page_Load(object sender, EventArgs e) {
}

protected void Register_Click(object sender, EventArgs e)
{
protected void Register_Click(object sender, EventArgs e) { SqlConnection con = new SqlConnection(ConfigurationManager.ConnectionStrings["dbconnection"].ConnectionString); con.Open(); SqlCommand cmd = new SqlCommand("insert into RegistrationTable values (@FirstName, @LastName, @Email, @MobileNumber, @Password)", con); cmd.Parameters.AddWithValue("FirstName", FnameTxt.Text); cmd.Parameters.AddWithValue("LastName", LnameTxt.Text); cmd.Parameters.AddWithValue("Email", Email.Text); cmd.Parameters.AddWithValue("MobileNumber", MobileNumber.Text); cmd.Parameters.AddWithValue("Password", Password.Text ); cmd.ExecuteNonQuery(); Label7.Visible = true; Label7.Text = "User registered successfully";
    FnameTxt.Text = "";
    LnameTxt.Text = "";
    Email.Text = "";
    MobileNumber.Text = "";
    Password.Text = "";
    FnameTxt.Focus();
}
}

TO CREATE THE LOGIN PAGE, WATCH THE FOLLOWING VIDEO ON YOUTUBE https://www.youtube.com/watch?v=QmT1oec1YBc
TO CREATE THE PROFILE PAGE, WATCH THE FOLLOWING VIDEO ON YOUTUBE https://www.youtube.com/watch?v=PCr2K4sHq6U
