---
author: "Khaled Hossain"
title: "How to create and activate a virtual environment in python?"
date: 2023-10-07T18:06:32-06:00
draft: false
description: "How to create and activate a virtual environment in python"
FAtags: ["python", "tutorial"]
FAcategories: ["python", "tutorial"]
---

## Follow these steps to create a virtual environment in python.


It is straightforward to create a virtual environment in Python. You can visit the  official documentation for creating Python environments here: https://docs.python.org/3/library/venv.html

We always want to create a virtual environment so that they are isolated from other environments. To create a virtual environment in Windows, you can run the following commands:

`python -m venv venv`

This will create a Python environment called venv using the system's python version.

**To activate**
Run the following: `.\venv\bin\Activate.ps1`

**To deactivate** 
Run the following: `deactivate`

Installing a Python environment with a **different version** of Python is also very easy, just have the path to the executable and then create the environment, for example: 

`C:\Users\Khaled\AppData\Local\Programs\Python\Python39\python.exe -m venv python39 `

**To activate:**
 `.\python39\Scripts\Activate.ps1 from my terminal. `

If you are using Visual Studio code. You can also hit **cntrl + shift + p** select python enterpretor and choose the new one you have created. 

And just like that you have got yourself a python environment.

*Happing coding!*