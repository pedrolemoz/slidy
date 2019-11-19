![Pub](https://img.shields.io/pub/v/slidy?color=orange)
[![GitHub stars](https://img.shields.io/github/stars/Flutterando/slidy?color=yellow)](https://github.com/Flutterando/slidy/stargazers)
[![Telegram](https://img.shields.io/badge/telegram-flutterando-blue)](https://t.me/flutterando)

[![Actions Status](https://github.com/AlvaroVasconcelos/slidy/workflows/Dart%20CI/badge.svg)](https://github.com/AlvaroVasconcelos/slidy/workflows/actions)
[![Actions Status](https://github.com/AlvaroVasconcelos/slidy/workflows/Example%20Android/badge.svg)](https://github.com/AlvaroVasconcelos/slidy/workflows/actions)
[![Actions Status](https://github.com/AlvaroVasconcelos/slidy/workflows/Example%20iOS/badge.svg)](https://github.com/AlvaroVasconcelos/slidy/workflows/actions)
[![Actions Status](https://github.com/AlvaroVasconcelos/slidy/workflows/Packages/badge.svg)](https://github.com/AlvaroVasconcelos/slidy/workflows/actions)
[![Actions Status](https://github.com/AlvaroVasconcelos/slidy/workflows/Tests/badge.svg)](https://github.com/AlvaroVasconcelos/slidy/workflows/actions)


[Acesse a documentação em Português-Brasil](README-PT.md)

# Slidy
CLI package manager and template generator for Flutter. Generate Modules, Pages, Widgets, BLoCs, Controllers and tests.

Slidy supports rxBLoC, flutter_bloc and mobx.

# Why should I use?

Slidy's goal is to help you structure your project in a standardized way. Organizing your app in **Modules** formed by pages, repositories, widgets, BloCs, and also create unit tests automatically. The Module gives you a easier way to inject dependencies and blocs, including automatic dispose. Also helps you installing the dependencies and packages, updating and removing them. The best is that you can do all of this running a single command.

# Motivations

We realized that the project pattern absence is affecting the productivity of most developers, so we're proposing a development pattern along with a tool that imitates NPM (NodeJS) functionality as well as template generation capabilities (similar to Scaffold ).

# About the Proposed Pattern

The structure that slidy offers you, it's similar to MVC, where a page keeps it's own **business logic classes(BloC)**. 

We recommend you to use [bloc_pattern](https://pub.dev/packages/bloc_pattern) when structuring with slidy. It offers you the **module structure**(extending the ModuleWidget) and dependency/bloc injection, or you will probably get an error. 

To understand **bloc_pattern package**, take a look at the [README](https://github.com/jacobaraujo7/bloc-pattern/blob/master/README.md).

We also use the **Repository Pattern**, so the folder structure it's organized in **local modules** and a **global module**. The dependencies(repositories, BloCs, models, etc) can be accessed throughout the application.

Sample folder structure generated by **slidy**:

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/folderw.png?raw=true)

## Installation


1. Activate the slidy using the pub:
    ```
    flutter pub global activate slidy
    ```
2. Type ` slidy --version` to make sure everything is working properly. This command should return the installed version.


## Commands: 

### upgrade:

Updates slidy's version:

```  
slidy upgrade
```   

### start:

Create the basic structure of your project (make sure that your "lib" folder it's empty).

```  
slidy start //default
slidy start --flutter_bloc
slidy start --mobx
```       
If you have the flutter_bloc or flutter_mobx package in pubspec, the generation of pages, widgets, and bloc defaults to the installed manager default.

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/start_cmd.png?raw=true)


### run:

Runs the scripts in pubspec.yaml:

```  
slidy run open_folder
```    

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/scripts.png?raw=true)

### install:

**Installs or update the packages in dependencies:** 

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/dependencies.png?raw=true)

```
slidy install rxdart dio bloc_pattern
``` 

or you can just use the **i** command (both are the same)

```
slidy i rxdart dio bloc_pattern
```

**Install packages as dev_dependency:**

```
slidy i mockito --dev
``` 

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/dev_d.png?raw=true)

### uninstall:

Removes a package
 ```
 slidy uninstall dio 
 ```
You can also remove a **dev_dependency** using the flag --dev


### generate:

Creates a module, page, widget or repository including its BloC class.

**NOTE:** You can replace "g" with "generate" command. 

Creates a new **module**:

``` 
slidy g module folder_name
``` 

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/module_cmd.png?raw=true)

Creates a new **page** + BloC:

```
slidy g page folder_name/pages
``` 
            
Creates a new **widget** + BloC:

```
slidy g widget folder_name/widgets
``` 

**NOTE:** You can create a page or widget using its respective BLoC using the flag **-b**

Create a new **repository**
```
slidy g r folder_name/repositories
``` 

Create a new **model**
```
slidy g mm folder_name/model
``` 

You can also use "repository" in "r"'s place, but it will have the same function.

![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/structure.png?raw=true)


## Unit Tests:

Generate **unit tests** on the test folder for you.

```
slidy test folder_name/
``` 

## Common errors:

**Windows:** 

  ![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/error_windows_install.jpg?raw=true)

  If you got this error when trying to run the ```pub global activate slidy```, then you will have to set the environment variables manually:

  * In windows search, write:  ```Edit System Variables```

  ![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/step1.png?raw=true)

  * Then click at ```Environment Variables```

  ![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/step2.png?raw=true)

  * Go to ```Path```

  ![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/step3.png?raw=true)

  * Then click in New and add the path that appeared on your console.

  ![Folder example](https://github.com/Flutterando/slidy/blob/master/screenshots/step4.png?raw=true)

If you have any doubt about setting up the system variables, watch [this](https://www.youtube.com/watch?v=bEroNNzqlF4) video.


For more details join our [Telegram Group Flutterando](https://t.me/flutterando)

