Download the driver Packages
You can download the ODBC Driver 17 for SQL Server from the official Microsoft website or using `wget` command directly in the terminal. Here's the command to download the driver packages:


`wget https://packages.microsoft.com/debian/9/prod/pool/main/m/msodbcsql17/msodbcsql17_17.9.1.1-1_amd64.deb`


Install the Driver:

once the packages is downloaded, you can install the `dpkg` command. Run the following command in the terminal:

`sudo dpkg -i msodbcsql17_17.9.1.1-1_amd64.deb`

Verify Installation:

`odbcinst -q -d`

Configure Connection parameters:
Update your connection parameters in your python script or notebook to use the newly intalled ODBC driver.

Restart Compute Instance (if necessary):
In some cases, you may need to restart your Azure MAchine Learning compute instance for the changes to effect. 
  




