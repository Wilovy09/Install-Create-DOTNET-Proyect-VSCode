# .NET 8 en Visual Studio Code con Arch Linux

## Instalación

Para instalar `dotnet` debemos de tener `yay` instalado

( Recomiendo hacer un `yay -Syu` antes de iniciar con la instalación )

```sh
yay -S dotnet-runtime dotnet-sdk aspnet-runtime
```

Y agregamos una variable a nuestro path (`.bashrc` ó `.zshrc`)

```sh
...

# Dotnet
export PATH=$PATH:~/.dotnet/tools
```

Para verificar que si se instalo correctamente

```sh
#sdk-options:
#    --info            Display .NET information.
#    --list-runtimes   Display the installed runtimes.
#    --list-sdks       Display the installed SDKs.
#    --version         Display .NET SDK version in use.

dotnet --version
# 8.0.101
```

## Cración de un proyecto

```sh
# Esto es para crear una nueva aplicación de consola
dotnet new console -n MiProyectoConsola

dotnet new classlib -n MiBiblioteca
dotnet new classlib -n MiBiblioteca --framework net8.0  
dotnet new classlib -n MiBiblioteca --framework netstandard2.0
dotnet new classlib -n MiBiblioteca --framework netstandard2.1

dotnet new mvc -n MiProyectoMvc

dotnet new webapi -n MiProyectoWebApi

dotnet new blazorwasm -n MiProyectoBlazorWasm

dotnet new xunit -n MiProyectoPruebas

dotnet new console -lang F# -n MiProyectoFSharp

dotnet new razor -n MiProyectoRazor
```

Hay muchos ejemplos de esto, y para poder ver todos los que tienes disponibles es mejor usar este comando

```sh
dotnet new list
```

```txt
$ dotnet new list  

These templates matched your input: 

Template Name                                 Short Name                  Language    Tags                      
--------------------------------------------  --------------------------  ----------  --------------------------
API Controller                                apicontroller               [C#]        Web/ASP.NET               
ASP.NET Core Empty                            web                         [C#],F#     Web/Empty                 
ASP.NET Core gRPC Service                     grpc                        [C#]        Web/gRPC/API/Service      
ASP.NET Core Web API                          webapi                      [C#],F#     Web/Web API/API/Service   
ASP.NET Core Web API (native AOT)             webapiaot                   [C#]        Web/Web API/API/Service   
ASP.NET Core Web App (Model-View-Controller)  mvc                         [C#],F#     Web/MVC                   
ASP.NET Core Web App (Razor Pages)            webapp,razor                [C#]        Web/MVC/Razor Pages       
Blazor Web App                                blazor                      [C#]        Web/Blazor/WebAssembly    
Blazor WebAssembly Standalone App             blazorwasm                  [C#]        Web/Blazor/WebAssembly/PWA
Class                                         class                       [C#],VB     Common                    
Class Library                                 classlib                    [C#],F#,VB  Common/Library            
Console App                                   console                     [C#],F#,VB  Common/Console            
dotnet gitignore file                         gitignore,.gitignore                    Config                    
Dotnet local tool manifest file               tool-manifest                           Config                    
EditorConfig file                             editorconfig,.editorconfig              Config                    
Enum                                          enum                        [C#],VB     Common                    
global.json file                              globaljson,global.json                  Config                    
Interface                                     interface                   [C#],VB     Common                    
MSBuild Directory.Build.props file            buildprops                              MSBuild/props             
MSBuild Directory.Build.targets file          buildtargets                            MSBuild/props             
MSTest Playwright Test Project                mstest-playwright           [C#]        Test/MSTest/Playwright    
MSTest Test Project                           mstest                      [C#],F#,VB  Test/MSTest               
MVC Controller                                mvccontroller               [C#]        Web/ASP.NET               
MVC ViewImports                               viewimports                 [C#]        Web/ASP.NET               
MVC ViewStart                                 viewstart                   [C#]        Web/ASP.NET               
NuGet Config                                  nugetconfig,nuget.config                Config                    
NUnit 3 Test Item                             nunit-test                  [C#],F#,VB  Test/NUnit                
NUnit 3 Test Project                          nunit                       [C#],F#,VB  Test/NUnit                
NUnit Playwright Test Project                 nunit-playwright            [C#]        Test/NUnit/Playwright     
Protocol Buffer File                          proto                                   Web/gRPC                  
Razor Class Library                           razorclasslib               [C#]        Web/Razor/Library         
Razor Component                               razorcomponent              [C#]        Web/ASP.NET               
Razor Page                                    page                        [C#]        Web/ASP.NET               
Razor View                                    view                        [C#]        Web/ASP.NET               
Record                                        record                      [C#]        Common                    
Solution File                                 sln,solution                            Solution                  
Struct                                        struct,structure            [C#],VB     Common                    
Web Config                                    webconfig                               Config                    
Worker Service                                worker                      [C#],F#     Common/Worker/Web         
xUnit Test Project                            xunit                       [C#],F#,VB  Test/xUnit       
```

## Ejecutar un programa

Tenemos que estar dentro de la carpeta de nuestro programa y ejecutar el siguiente comando:

```sh
dotnet run
```
