Download Link: https://assignmentchef.com/product/solved-dbs211-lab7-sql-database-application-development
<br>
Objective:

In this lab students learn:

<ul>

 <li>How to connect to a Oracle server from a C++ program.</li>

 <li>How to write and execute SQL queries in a C++ program.</li>

</ul>

<h1>Getting Started Instructions:</h1>

<h1>Create Oracle Server Connection:</h1>

To connect to the Oracle server from your C++ program in Visual Studio, you need to follow these steps:

Download the Oracle Instant Client SDK and libraries from for version 12.2.0.1.0 from <a href="http://dbs211.ca/files/instantclient_12_2.zip">http://dbs211.ca/files/instantclient_12_2.zip</a>.  Extract the zip archive to a local folder on your hard drive.

Open Visual Studio and create a new C++ console project.  If you do not have visual studio installed, you can obtain it from MyApps at Seneca College or you can download the free Visual Studio Community Edition at: <a href="https://visualstudio.microsoft.com/vs/community/">https://visualstudio.microsoft.com/vs/community/</a>

Once you have created the project:

The first step in the project is to establish that it is a .cpp project, so create a cpp file by right clicking on the “Source Files” folder and choosing “Add – new Item”.  Choose a C++ File (.cpp) and enter a name of choice, I suggest something like “<em>DBS211_DB_Connection_Test.cpp</em>”.

In the top of the file write the 2 includes below:

#include &lt;iostream&gt;

#include &lt;occi.h&gt;

and save the file.

To connect and work with databases in Oracle server, we use the &lt;<em>occi.h&gt;</em> header file or library. To set up the visual configuration, right click on your project name in the navigation bar and go to “Properties”:

<h2>Project/Properties</h2>

In the “Configuration” dropdown on the top-left, change to “release” and change “Platform” to “x64” and select “Apply”.

This previous step ensures that the Visual Studio project is set to release so other properties that are set apply to this version.  In real life programming, you would work in Debug version until all testing is done, then change to release and test again.

Configuration Properties

In property Page, under Configuration Properties click on “C/C++” and then “General”.  On the right side click the drop-down arrow beside “Include Directories” and choose “edit”.

<h4>Linking to the Includes Folder to reference the “occi.h” header file required for the project.</h4>

On the new screen (shown right), click on the currently blank top line of the first box and you will see a “…” button.  Click on this button and navigate to the folder where you extracted the Instant Client SDK and then into the “include” folder, click “Select Folder”.   Note: your path may be different then the one shown below as it will depend on where you extracted the instant client SDK zip archive.

Click OK and then Apply.

<h3>Linking to the Required Libraries</h3>

Now we need to tell the application where the library files we will be referencing are found.  Navigation the Configuration Properties to Linker and then General

Under Additional Library Directories you will include a reference to the libraries folder:

instantclient_12_2sdklibmsvcvc14  – relative to your zip archive extraction location.

You will then be required to tell the application which library we need to use.

Under Linker / Input / Additional Dependencies, you will need to add oraocci12.lib.

And lastly you will need to add the oraocci12.dll file to your project folder directory.  Right click on the Project and choose: “Open Folder in File Explorer”.  This is the folder where the .dll file must be placed.   The required file can be copied from the main instantclient_12_2 folder.

Finally make sure that everything seems okay to this point by trying to build the project.  An error free build is the first good sign.

<strong><em>Connecting to an Oracle database from a C++ Program</em></strong>

So now we will add some code to make sure we can connect we can do a simple test.  In the .cpp file we created earlier, type in the following code to test your connection.  It is important that you type it as to learn what is happening to make completing the project tasks much easier.  (Hence why I am providing a screen shot rather than text so you cannot copy and paste)

If you see the console screen come up with Connection is Successful, then you are ready to move to the next steps.

<h2>Running a Simple SELECT query and outputting the results</h2>

So we will go through a series of steps to get some output.  Type in the following code as shown within the code shown above…. (i.e. merge the two).  Use the provided information in class (likely a PPT slideshow) to understand what each line is doing.  Some key concepts you will want to understand include:

<ul>

 <li>Connection (conn)</li>

 <li>RecordSet (rs)</li>

 <li>next() method and how it works</li>

 <li>and all the terminate statements and why they are necessary.</li>

</ul>




<strong>Lab Requirements:</strong>

In this lab, you need to write a C++ program to execute the following queries and display the result returned by each query. For the output format, see the sample output.

<ol>

 <li>Display Employee Number, First Name, Last Name, Phone Number, and Extension of all Employees who work in San Francisco. See the following Sample output.</li>

 <li>Display Employee Number, Last Name, Phone Number, and Extension for all managers. (You can use column reportsto to find the managers’ employee numbers)</li>

</ol>

Sample output:








