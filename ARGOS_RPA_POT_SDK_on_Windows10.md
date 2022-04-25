![top-header](Captures/top-header.png)

# The 5 templates and 3 utilities
> What you need: Python 3.7 and PyCharm

|Index | Icon | Items |
|:---:|---|---|
***1.*** | ![top-01-01](Captures/top-01-01.png) | ***Your Python program (sample API code, OSS, or your original Python code)***
***2.*** | ![top-01-02](Captures/top-01-02.png) | ***Template 1: requirements.txt → define referenced resources***
***3.*** | ![top-01-03](Captures/top-01-03.png) | ***Template 2: at __init__.py → design your parameter input***
***4.*** | ![top-01-04](Captures/top-01-04.png) | ***Template 3: at __init__.py → design the main program body***
***5.*** | ![top-01-05](Captures/top-01-05.png) | ***Template 4: test_me.py → run unit test at the Python level***
***6.*** | ![top-01-06](Captures/top-01-06.png) | ***Template 5: setup.yaml → set attributes for search on STU***
***7.*** | ![top-01-07](Captures/top-01-07.png) | ***Utility 1: alabs.icon → design the plugin icon from any graphics***
***8.*** | ![top-01-08](Captures/top-01-08.png) | ***Utility 2: build.bat → prepare upload-able package (.whl)***
***9.*** | ![top-01-09](Captures/top-01-09.png) | ***Utility 3: Preconfigured Test Repository***

# 13 useful rules to keep in mind
> to avoid errors that we see frequently

## Related to the Python package name
1. ***Always start with “argoslabs” like argoslabs.anyname1.anyname2.***
2. ***Package name must have three levels like argoslabs.anyname1.anyname2.***
3. ***You can only use lowercase of a ~ z and underscore (_) for the package name.***
4. ***Package name must be unique (Don’t worry – there is a checking mechanism when packaging).***
5. ***Display name must be unique (Don’t worry – there is a checking mechanism when packaging).***

## Related to configuring setup.yaml file
6. ***You must declare platforms like [‘windows’, ‘darwin’, ‘linux’].***
7. ***Set proper keywords.***
8. ***Set proper platform.***
9. ***Set version like 1.2.3.4 (Do not start the section with 0, i.e., 1.505.0935 is not allowed.***
10. ***Do not forget to enter the proper package name at package_data.***

## Related to plugin coding
11. ***Design input and output to be user friendly.***
12. ***Print out to STDOUT with a good result. The Return Value can be used as String, CSV or File at STU.***
13. ***Design with good exception handling and Return Code. The Return Code can be handled at STU.***


---

# ARGOS-Labs POT SDK on Windows 10

Welcome to the Python-to-Operation Toolset (POT) SDK for ARGOS Low-code platform. This doucoment will show you how to develop and release a plugin from your Python solution.

## Prerequisites

Before your start, let's prepare your POT SDK environment. There are 3 pieces of software you need to install.
- Python interpreter
- The POT SDK
- IDE (PyCharm)

Oh, btw, we are assuming you already have signed up with [ARGOS Supervisor account](https://rpa.argos-labs.com/), downloaded the latest version of STU and PAM from the [ARGOS LABS website](https://www.argos-labs.com/#download), and installed them successfully.

### [Installing Python Interpreter](Install_Python_Interpreter_Windows10.md)

You will need **Python 3.7.3 32bit on Windows 10**. Please select the **32bit** version even when your OS is 64bit because of compatibility reasons.

### [Installing ARGOS POT SDK](Install_ARGOS_POT_SDK_Windows10.md)

ARGOS POT SDK consists of three components as follows:

| Item | Minimum version | Role | Description |
|---|---|---|---|
| [alabs.common](https://pypi-official.argos-labs.com/#/package/alabs-common) | 3.721.1350 | SDK library | Library for SDK |
| [alabs.icon](https://pypi-official.argos-labs.com/#/package/alabs-icon) | 1.711.2351 | icon utility | This utility make plugin icon |
| [alabs.ppm](https://pypi-official.argos-labs.com/#/package/alabs-ppm) | 4.115.1700 | POT utility | POT main utility |


### [Installation of PyCharm IDE](Install_PyCharm_Windows10.md)

This guide is based on one of the most popular Python [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment)
* `PyCharm` Community Edition

## How to build a ARGOS Low-Code Python Plugin

The step by step guide for how to build ARGOS Low-Code Python plugin.

#### [Download the plugin template](Download_Template.md)

When starting a new project, you must prepare a base folder from `Template` everytime. Then, you must set configuration for `PyCharm` IDE.
You can download the `Template` folder in which you will find several files including 

#### [PyCharm settings](PyCharm_Settings_Windows10.md)
You must complete the IDE settings after preparation of Template.

## Coding for plugin
This document will show you how to code from the scaffolding template.

### [Setting the package name](Set_Package_name_Windows10.md)

You need to change python package name from `argoslabs.demo.helloworld` to `argoslabs.myplugin.asciiart` for example.

### [Sample code and dependent module](Install_Dependent_modules_Windows10.md)

When your plugin requires installation of any third party modules (dependent modules) from [pypi.org](https://pypi.org). This guild will show you how to do it.

### [Coding your main Python program at `__init__.py`](Main_Coding_Windows10.md)

Plugin's main code is made from the source, `argoslabs/myplugin/asciiart/__init__.py`.

### [Testing and validating for the unique name](Testing_Windows10.md)

Every code needs to be tested as much as possible. Also, it is required to have a unique name for your package like `argoslabs.gourp.plugin_name` and for your display name that will appear under `STU`'s Icon. This guild will show you how to test your plugin with unittest and to check for the unique names. 

### [Tags and Version](Setup_yaml.md)
Before building the plugin you have to set tags and version for that plugin.

### [Writing the help document with README.md](Usage_Help_with_README.md)
Each plugin must have a usage help. The README.md contents will be linked the STU's help button. This guide shows how to make this help contents.

## Building your plugin

Now that everything is ready. Let's build your plugin.

### [Preparing private repository](Preparing_Private_Repository_Windows10.md)

After building your plugin, you can upload it to your own Python private repository. This guide shows how to install private repository and configuration at Supervisor.

### [Creating an icon for your plugin](build_icon_plugin_Windows10.md)
You must select a fitting image and make an icon using `alabs.icon` utility and then you can build this plugin with `build.bat` batch file.

## After making plugin

Once you build your own plugin, it's time to make a bot with `STU` for testing. And you may need to upgrade the plugin if needed.

### [How to make a test bot with STU](Make_testing_bot_STU.md)

Now your plugin is registered at private repository so you can make use of this plugin. This guide shows how to make a bot using your plugin.

### [How to upgrade/remove(EOL) your plugin](How_to_Upgrade_plugin.md)
Because plugin is a normal software it need to fix or upgrade if needed. This guide shows how to upgrade your plugin.
