For .Net Core 6.0 LTS MVC projects (user logins = individual accounts = SQL dB)

Possible Errors:
"CREATE FILE encountered operating system error 5A(Access denied.) while attempting to open or create the physical file "CProgram FilesMSSQL"
Bug causes missing backslash in path
Fix: Install HotFix for SQL Server 2017 (SQL Server 14.0.xxxx) https://www.microsoft.com/en-us/download/confirmation.aspx?id=56128



edit appsettings.json , add to connection string: ;Trust Server Certificate=true
SQL Local Instance: (localdb)\MSSQLLocalDB
Otherwise if you have an existing empty dB elsewhere fix ConnectionString

cd into project directory (where .csproj is and run:

dotnet list package

# use the version from list package eg 6.0.15
dotnet add package Microsoft.EntityFrameworkCore.Design --version 6.0.15

dotnet ef database update

