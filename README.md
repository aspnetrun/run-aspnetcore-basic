# What is AspnetRun ? 
A **starter kit** for your next **ASP.NET Core** web application. Boilerplate for **ASP.NET Core reference application** with **Entity Framework Core**, demonstrating a layered application architecture with DDD best practices. Implements NLayer **Hexagonal architecture** (Core, Application, Infrastructure and Presentation Layers) and **Domain Driven Design** (Entities, Repositories, Domain/Application Services, DTO's...) 
and aimed to be a **Clean Architecture**, with applying **SOLID principles** in order to use for a project template. 
Also implements **best practices** like **loosely-coupled, dependency-inverted** architecture and using **design patterns** such as **Dependency Injection**, logging, validation, exception handling, localization and so on.

You can check full repository documentations and step by step development of **[100+ page eBook PDF](http://www.aspnetrun.com/Book)** from here - **http://www.aspnetrun.com/Book**. Also detail introduction of book and project structure exists on **[50+ page of github wiki](https://github.com/aspnetrun/run-core/wiki)**. You can follow **aspnetrun repositories** for building **step by step** asp.net core **web development skills**.

# AspnetRun Repositories
Here you can find all of the **aspnetrun repositories from easy to difficult**, Also this list can be track a **learning path** of asp.net core respectively;
* **[run-aspnetcore-basic](https://github.com/aspnetrun/run-aspnetcore-basic)** - intented to building Multi-Page Web Applications(MPA) using ASP.NET Core Default Web Application template with EF.Core. This solution **only one solution one project** fastest **idea generation** with Asp.Net Core. **YOU ARE HERE.**
* **[run-aspnetcore](https://github.com/aspnetrun/run-aspnetcore)** - intented to building traditional Multi-Page Web Applications(MPA) using ASP.NET Core & EF.Core and **Razor Pages** templates with default aspnet core server-side rendering approach.
* **[run-aspnetcore-spa](https://github.com/aspnetrun/run-aspnetcore-spa)** - intented to building **Single-Page Web Applications(SPA)** using only ASP.NET Core **without any frontend framework**. This comes with **Blazor** framework in asp.net core 3.x.
* **[run-angular](https://github.com/aspnetrun/run-angular)** - intented to building Single-Page Web Applications(SPA) using ASP.NET Core & EF.Core, Web API Project and **Angular** for frontend framework.

And there are crucial repositories which are **implemented base repository** and **applying real-world examples** with developing new enterprice features for example Identity, Paging, Localization etc..
* **[run-aspnetcore-basic-realworld](https://github.com/aspnetrun/run-aspnetcore-basic-realworld)** - implemented this repository and build **sample of eCommerce reference application** on Multi-Page Web Applications(MPA) using ASP.NET Core in a **one solution one project for fastest idea implementations**.
* **[run-aspnetcore-realworld](https://github.com/aspnetrun/run-aspnetcore-realworld)** - implemented run-aspnetcore repository and build **sample of eCommerce reference application** on Multi-Page Web Applications(MPA) using ASP.NET Core Razor Pages templates.
* **[run-aspnetcore-spa-realworld](https://github.com/aspnetrun/run-aspnetcore-spa-realworld)** - implemented run-aspnetcore-spa repository and build **sample of eCommerce reference application** on **Single-Page Web Applications(SPA)** using ASP.NET Core Blazor Pages templates.
* **[run-angular-realworld](https://github.com/aspnetrun/run-angular-realworld)** - implemented run-angular repository and build **sample of eCommerce reference application** on Single Page Web Application(SPA) architecture using **ASP.NET Core + Angular**.

These repositories are **updated regularly**. We are following Microsoft Web Technologies very closely so we will update all these repositories accordingly with **Microsoft Web Application stacks**.

# run-aspnetcore-basic
Here is CRUD operations of aspnetrun-core-basic template project;

![Recordit GIF](http://g.recordit.co/LJCyYfQEpX.gif)

**run-aspnetcore-basic** is a general purpose to implement the **Default Web Application template of .Net** with **one solution one project for fastest idea implementations** to building modern web applications with latest ASP.NET Core & Web API & EF Core technologies. 

## Give a Star! :star:
If you liked the project or if AspnetRun helped you, please **give a star**. And also please **fork** this repository and send us **pull-requests**. If you find any problem please open **issue**.

## Getting Started
Use these instructions to get the project up and running.

### Prerequisites
You will need the following tools:

* [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/)
* [.Net Core 2.2 or later](https://dotnet.microsoft.com/download/dotnet-core/2.2)
* EF Core 2.2 or later

### Installing
Follow these steps to get your development environment set up:
1. Clone the repository
2. At the root directory, restore required packages by running:
```csharp
dotnet restore
```
3. Next, build the solution by running:
```csharp
dotnet build
```
4. Next, within the AspnetRun.Web directory, launch the back end by running:
```csharp
dotnet run
```
5. Launch http://localhost:5400/ in your browser to view the Web UI.

If you have **Visual Studio** after cloning Open solution with your IDE, AspnetRun.Web should be the start-up project. Directly run this project on Visual Studio with **F5 or Ctrl+F5**. You will see index page of project, you can navigate product and category pages and you can perform crud operations on your browser.

### Usage
After cloning or downloading the sample you should be able to run it using an In Memory database immediately. The default configuration of Entity Framework Database is **"InMemoryDatabase"**.
If you wish to use the project with a persistent database, you will need to run its Entity Framework Core **migrations** before you will be able to run the app, and update the ConfigureDatabases method in **Startup.cs** (see below).

```csharp
public void ConfigureDatabases(IServiceCollection services)
{
            //// use in-memory database
            //services.AddDbContext<AspnetRunContext>(c =>
            //    c.UseInMemoryDatabase("AspnetRunConnection"));

            // add real database dependecy
            services.AddDbContext<AspnetRunContext>(c =>
                c.UseSqlServer(Configuration.GetConnectionString("AspnetRunConnection")));  
}
```

1. Ensure your connection strings in ```appsettings.json``` point to a local SQL Server instance.

2. Open a command prompt in the Web folder and execute the following commands:

```csharp
dotnet restore
dotnet ef database update -c AspnetRunContext
```
Or you can direct call ef commands from Visual Studio **Package Manager Console**. Open Package Manager Console, set default project to AspnetRun.Infrastructure and run below command;
```csharp
update-database
```
These commands will create aspnetrun database which include Product and Category table. You can see from **AspnetRunContext.cs**.
1. Run the application.
The first time you run the application, it will seed aspnetrun sql server database with a few data such that you should see products and categories.

If you modify-change or add new some of entities to Core project, you should run ef migrate commands in order to update your database as the same way but below commands;
```csharp
add-migration YourCustomEntityChanges
update-database
```

## Layered Architecture
AspnetRun implements NLayer **Hexagonal architecture** (Core, Application, Infrastructure and Presentation Layers) and **Domain Driven Design** (Entities, Repositories, Domain/Application Services, DTO's...). Also implements and provides a good infrastructure to implement **best practices** such as Dependency Injection, logging, validation, exception handling, localization and so on.
Aimed to be a **Clean Architecture** also called **Onion Architecture**, with applying **SOLID principles** in order to use for a project template. Also implements and provides a good infrastructure to implement **best practices** like **loosely-coupled, dependency-inverted** architecture
The below image represents aspnetrun approach of development architecture of run repository series;

![DDD_png_pure](https://user-images.githubusercontent.com/1147445/54773098-e1efe700-4c19-11e9-9150-74f7e770de42.png)

### Structure of Project
AspnetRunBasic has only **one solution** and into this solution only **one web application project** which include all components of project structure. The idea is that **fast implementation, minimum development, bootstrap your idea, create Minimum Viable Product (MVP), idea validation, startup development implementation** for a **limited time** and **limited resources** with using asp.net core and entity framework core. 

Repository include folders for group implementations;
* Data
    * AspnetRunContext    
    * AspnetRunContextSeed    
* Entities
    * Product    
    * Category    
* Migrations
    * Generated by scaffolding from ef.core    
* Pages
    * Default Razor Web Application Template of Asp.Net Core
* Repositories
    * IProductRepository
    * ProductRepository
    
### Data Folder
Includes **Entity Framework Core Context** and tables in this folder. When new entity created, it should add to context and configure in context.
The Infrastructure project depends on Microsoft.**EntityFrameworkCore.SqlServer** and EF.Core related nuget packages, you can check nuget packages of Infrastructure layer. If you want to change your data access layer, it can easily be replaced with a lighter-weight ORM like Dapper. 

#### Migrations
EF add-migration classes.
#### Repository
EF Repository implementation. This class responsible to create queries, includes, where conditions etc..

#### Entities Folder
Includes Entity Framework Core Entities which creates sql table with **Entity Framework Core Code First Aproach**. Some Aggregate folders holds entity and aggregates.
You can see example of **code-first** Entity definition as below;

```csharp
public class Product
    {
        public int Id { get; set; }

        [Required, StringLength(80)]
        public string Name { get; set; }

        [Required, StringLength(255)]
        public string Description { get; set; }

        public int UnitPrice { get; set; }        

        public int CategoryId { get; set; }
        public Category Category { get; set; }
    }
```

### Repository Folder
Implementation of Core interfaces in this project with **Entity Framework Core** and other dependencies.
Most of your application's dependence on external resources should be implemented in classes defined in the Infrastructure project. These classes must implement the interfaces defined in Core. If you have a very large project with many dependencies, it may make sense to have more than one Infrastructure project (eg Infrastructure.Data), but in most projects one Infrastructure project that contains folders works well.
This could be includes, for example, **e-mail providers, file access, web api clients**, etc. For now this repository only dependend sample data access and basic domain actions, by this way there will be no direct links to your Core or UI projects.

```csharp
public interface IProductRepository
    {
        Task<IEnumerable<Product>> GetProductListAsync();
        Task<Product> GetProductByIdAsync(int id);
        Task<IEnumerable<Product>> GetProductByNameAsync(string name);
        Task<IEnumerable<Product>> GetProductByCategoryAsync(int categoryId);
        Task<Product> AddAsync(Product product);
        Task UpdateAsync(Product product);
        Task DeleteAsync(Product product);
        Task<IEnumerable<Category>> GetCategories();
    }
```
Also implementation located same places in order to choose different implementation at runtime when DI bootstrapped.
```csharp
 public class ProductRepository : IProductRepository
    {
        protected readonly AspnetRunContext _dbContext;

        public ProductRepository(AspnetRunContext dbContext)
        {
            _dbContext = dbContext ?? throw new ArgumentNullException(nameof(dbContext));
        }

        public async Task<IEnumerable<Product>> GetProductListAsync()
        {
            return await _dbContext.Products.ToListAsync();
        }

        public async Task<Product> GetProductByIdAsync(int id)
        {
            return await _dbContext.Products
                .Include(p => p.Category)
                .FirstOrDefaultAsync(p => p.Id == id);
        }
```


### Pages Folder
Development of UI Logic with implementation. Interfaces drives business requirements and implementations in this layer.
The application's main **starting point** is the ASP.NET Core web project. This is a classical console application, with a public static void Main method in Program.cs. It currently uses the default **ASP.NET Core project template** which based on **Razor Pages** templates. This includes appsettings.json file plus environment variables in order to stored configuration parameters, and is configured in Startup.cs.


## Technologies
* .NET Core 2.2
* ASP.NET Core 2.2
* Entity Framework Core 2.2 
* .NET Core Native DI
* Razor Pages
* AutoMapper

## Used Components
* Asp.Net Core
* Entity Framework Core
* Razor Pages
* Repository Design Pattern
* Multiple Page Web Application (MPA)
* Monolitic Deployment Architecture
* SOLID and Clean Code

## Disclaimer

* This repository is not intended to be a definitive solution.
* This repository not implemented a lot of 3rd party packages, we are try to avoid the over engineering when building on best practices.
* Beware to use in production way.

## Contributing

Please read [Contributing.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/aspnetrun/run-core/tags). 

## Next Releases and RoapMap

For information on upcoming features and fixes, take a look at the [product roadmap](https://github.com/aspnetrun/run-core/projects).

## Deployment - AspnetRun Online

This project is deployed on Azure. See the project running on Azure in [here](aspnetrun.com).

## Pull-Request

Please fork this repository, and send me your findings with pull-requests. This is open-source repository so open to contributions.

## Authors

* **Mehmet Ozkaya** - *Initial work* - [mehmetozkaya](https://github.com/mehmetozkaya)

See also the list of [contributors](https://github.com/aspnetrun/run-core/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details
