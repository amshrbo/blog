---
title: "Virtual environments in Python"
date: 2021-12-25T20:50:13+02:00
description: "Everything you need to know about virtual environments for Python"

tags: ['python', 'virtualenv', 'linux']
categories: ['python', 'linux']
ShowToc: true
ShowCodeCopyButtons: true
---
![Python virtualenv](/Virtual_Environments_in_Python.png)
> As we all know python is a multi purpose programmng language, and their applications goes from simple automation scripts for renaming your files, creating desktop apps, mobile apps, web apps, to use cutting edge packages designed for machine learning and data science, so how to manage all of these packages in a single machine avoiding the hassle of package confilcts and debendancies issues.

### Introduction, motivation and Answering your Questions:
1. __Why we need Virtual environments__

1. __Why to use virtualenv instead of any other tool ?__

1. __Why we need Virtual environments__

1. __Why to use virtualenv instead of any other tool ?__

---
### How do I manage virtual environments in python?

#### Installing virtualenv:
- `$ python -m pip install --user virtualenv`

- Append virtualenv path to the bin path you will find it under /usr/.local/bin:
    1. Restart your terminal session
    1. find the absolute path for virtualenv: `$ which virtualenv`
    1. In my case it's in `$ /home/shrbo/.local/bin/virtualenv`
    1. `$ export PATH=/home/shrbo/.local/bin:$PATH` 
    1. Showing your path content `$ echo $PATH`  make sure virtualenv path appear

---
#### The file hierarchical for managing different environments:
The below dir hierarchical which I use for managing different envs in the same machine

```
python-working
|
|__ venvs
|   |
|   |__ flask
|   |
|   |__ tensorflow-gpu
|   |
|   |__ webdev
|
|__ projects
    |
    |__ tech-blog
    |
    |__ stacked-autoencoders
```
> So what is going on here: creating two folders one for venvs and the other for projects, under venvs folder I can go and create any enviroment, then I go and activte that environment go back to the project that I want and get work done.	

---
#### _Lab_ creating an environment for a blog:
+ _Creating your dirs_ `mkdir venvs && cd venvs`		

+ `$ virtualenv --python=$(which python3) webdev`			
    > - `--python=` specifing the full python version path 
    > - `webdev` the name of the environment

+ _Activate the venv_ **Bash shell** `$ source webdev/bin/activate`		

+ _Activate the venv_ **Fish shell** `$ . webdev/bin/activate.fish`		

+ _install required libs using pip_ `$ pip3 install flask`		

+ _Start working on your project_ `$ cd ../projects && mkdir new-blog`	

+ _To deactivate the venv_ `$ deactivate`		

+ _removing venv_ `$ rm -rf webdev` 	

---
#### Integrate your virtualenvs with vscode:
> So as we see above we have a folder for virtualenv and I use vscode   

1. First go to vscode and hit `ctrl + ,` to open the settings  
2. Choose the user settings tab and type in the search `python venv`  
3. Type the absolute path for the venvs folder in the `/home/shrbo/python_working/venvs`
4. Restart vscode  
5. Hit `ctrl + shift + p` and type `python: select interpreter` then hit `return`  
6. Choose the virtualenv that you want an hit `return`  :thumbs_up: :thumbs_up:

---