*****************************************************************
XML Parser - 
Developed By: Azqa Nadeem, DSLab Internee
Date: 26/06/2014
*****************************************************************


Compiling and Running XMLparser on Linux
----------------------------------------

The XML parser compiles and runs on Linux using the Mono framework:

1. Install Mono on your computer::

        sudo aptitude install mono-devel

2. Add the MySQL connector to the mono assembly cache::

        sudo gacutil -i packages/MySql.Data.6.8.3/lib/net45/MySql.Data.dll

3. Compile the XML parser::

        make

   This creates a file called bin/Program.exe, and a corresponding settings
   file bin/Program.exe.config. Edit the latter in order to specify the
   database connection information.

4. Run the XML parser::

        mono bin/Program.exe /path/to/nvdcve-XXX.xml Password-of-your-Database

About XML Parser
----------------------------------------

This program first reads the xml file and then tries to parse it by using the code in NanoXMLParser.cs. After it verifies

the XML itself is error free, it starts looking for nodes related to entry and then drills down to find more information

needed by us to store in the database.All such information is stored in structures having appropriate data fields and then

finally are saved to the database by using MySQL queries.

If any exception occurs, the program is aborted after showing the error message.
