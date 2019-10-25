# SSMS Partition Details Custom Reports
Custom reports for SQL Server Management Studio that list table and indexed view row counts, partition boundaries, and space information. This RDL uses the standard Custom report framework introduced in SQL Server 2005 SP2.

The basic Partition Details report lists tables and indexed views in the context database including: 
- Object name 
- Index name 
- Rows (object and partition level) 
- Partition Number 
- Partition Lower Boundary (partitioned objects only) 
- Partition Upper Boundary (partitioned objects only) ,
- Partition Function Range (LEFT or RIGHT) (partitioned objects only) 
- Partition Scheme (partitioned objects only) 
- File Group Name

The Partition Details With Space Information report also includes: 
- Used Pages 
- Used Space (KB) 
- Reserved Pages 
- Reserved Space (KB)

<b>System Requirements</b>
-  SQL Server Management Studio 2005 SP2 or above.

<b>Installation instructions</b><br>
Copy files "Partition Details.rdl" and "Partition Details With Space Information.rdl" to a folder that is accessable to the SSMS client. This can be a local folder or network share.

<b>Security Considerations</b><br>
<b>Before running this or any other SSMS custom report obtained from a third party, view the RDL file source with an editor to ensure the report does not contain malicious embeded SQL code.</b> The query used in this report selects from system catalog views so the current user requires VIEW DEFINITION permission on the reported objects. This is the same permission needed for objects to be visible in the SSMS Object Explorer tree so no additional user security needs to be granted.

<b>Usage</b><br>
To run the report for a single table or indexed view, right-click on the desired object in SSMS Object explorer. Select "Custom Reports..." and browse to the location of the "Partition Details.rdl" or "Partition Details With Space Information.rdl" file. SSMS will remember the report after first use as a recently used report for convenient execution directly from the Reports context memu going forward. The report will include all tables and indexed views in the current database when run in the context of any other node type (i.e. not a table or view) under the Databases folder. If the report is run outside of a database folder tree context, an error will be displayed indicating that the DatabaseName value is missing. 

