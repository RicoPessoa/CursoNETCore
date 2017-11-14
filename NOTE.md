## Video 01

**Link's** 
- https://dotnetfoundation.org
- https://github.com/aspnet/home

## Video 02

**Link's**
- https://www.microsoft.com/net/
- https://github.com/dotnet/cli
&nbsp;

Comandos no CLI para criar um nova aplicação e rodar ela
```
dotnet new
dotnet restore
dotnet run
```

## Video 03

Criar um novo projeto .NET Core 2.0 no Visual Studio 2017 (*File \ New \ Project \ ASP.NET Core Web Application*)

## Video 04

**Link's** 
- http://owin.org/spec/spec/owin-1.0.0.html

- As principais interfaces
```
IConfigurationRoot
IHostingEnvironment
IServiceColletion
IApplicationBuilder
ILoggerFactory

install-package Microsoft.Extensions.Configuration.UserSecrets
```

- UserSecrets ASP.NET Core 1.0.1 e 1.1.0
```
        public Startup(IHostingEnvironment env)
        {
            var builder = new ConfigurationBuilder()
                .SetBasePath(env.ContentRootPath)
                .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
                .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true);


            // User Secrets
            if (env.IsDevelopment())
            {
                builder.AddUserSecrets();
            }

            builder.AddEnvironmentVariables();
            Configuration = builder.Build();

        }
```
- UserSecrets ASP.NET Core 2.0.0
```
        public Startup(IHostingEnvironment env)
        {
            var builder = new ConfigurationBuilder()
                .SetBasePath(env.ContentRootPath)
                .AddJsonFile("appsettings.json", optional: false, reloadOnChange: true)
                .AddJsonFile($"appsettings.{env.EnvironmentName}.json", optional: true);


            // User Secrets
            if (env.IsDevelopment())
            {
                builder.AddUserSecrets<Startup>();
            }

            builder.AddEnvironmentVariables();
            Configuration = builder.Build();

        }
```

## Video 5

- Não está funcionando esse comando no VS 2017


```
@tagHelperPrefix
```
