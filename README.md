# RazorPagesMovie
ASP.NET Core Web App (Razor Pages) Project

## Technologies Used

- **ASP.NET Core**: A framework for building web applications, using .NET 8.0.
- **Razor Pages**: A technology for simplifying the creation of web application pages.
- **Entity Framework Core**: An ORM for database operations.
- **SQL Server**: A database management system.
- **Rider IDE**: An integrated development environment for .NET applications.

## Set Up the Data Model

1. In Rider IDE, right-click the `RazorPagesMovie` project, then select `Add` > `New Folder`. Name the folder `Models`.
2. Right-click the `Models` folder, select `Add` > `Class`, and name the class `Movie`.

## Scaffold the Razor Pages

1. Create a `Movies` folder inside the `Pages` folder:
   - Right-click on the `Pages` folder > `Add` > `New Folder`, and name it `Movies`.

2. Right-click on the `Pages/Movies` folder > `Add` > `New Scaffolded Item`. Select `Razor Pages using Entity Framework (CRUD)`.

3. Complete the dialog:
   - In the **Model class** dropdown, select `Movie (RazorPagesMovie.Models)`.
   - In the **Data context class** row, click the `+` sign.
   - In the **Add Data Context** dialog, ensure the class name `RazorPagesMovie.Data.RazorPagesMovieContext` is generated.
   - Select `SQL Server` in the **Database provider** dropdown.
   - Click `Add`.

The `appsettings.json` file will be updated with the connection string for a local database.

## Install Required Tools/Packages

Install the .NET EF tools globally if not already installed:

```
dotnet tool install --global dotnet-ef
```
This tool is used for managing Entity Framework Core migrations and database updates.

```
dotnet add package Microsoft.EntityFrameworkCore.Design
```
This package provides the design-time tools required for Entity Framework Core, such as generating and applying migrations.

## Update the Database

For Rider IDE, the Package Manager Console (PMC) cannot be used, so use the terminal instead.

1. **Add an initial migration:**

   ```
   dotnet ef migrations add InitialCreate
   ```

This command generates code to create the initial database schema based on the DbContext model.

2. **Update the database with the migration**

```
dotnet ef database update
```

This command applies the migration to create the database.

## Run the Project

```
dotnet run
```


