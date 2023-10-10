# Create a Python GPT Chatbot

## Project Setup

Download a text editor, such as VSCode or Sublime Text. (I prefer VSCode)

[Link to Download VSCode](https://code.visualstudio.com/download)

[Link to Download Sublime Text](https://www.sublimetext.com/)

In the VSCode Terminal/Command Prompt, setup the local project directory:

```sh
mkdir python_gpt_chatbot
cd python_gpt_chatbot
```

Head to [Github](https://github.com/) and create a new remote repository named `python_gpt_chatbot`.

Following the creation of your new remote repository, create a new local repository on the command line:

```sh
echo "# python_gpt_chatbot" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/MylesThomas/python_gpt_chatbot.git
git push -u origin main
```

Save this file as a markdown file `python_gpt_chatbot/instructions.md`, then open up a new VSCode instance and Open folder > `python_gpt_chatbot`.

Next, setup a virtual Python environment:

```sh
cd python_gpt_chatbot
py -m venv env
```

You should now see a folder 'env' with a python.exe program in the /Scripts directory.

Create a .gitignore file for the Python project and save it in the root directory `python_gpt_chatbot`:

```sh
cd python_gpt_chatbot
echo > .gitignore
```

Code for .gitignore: [Link to file](https://github.com/github/gitignore/blob/main/Python.gitignore)

Activate the virtual environment in the terminal:

```sh
where python
.\env\Scripts\activate

python.exe -m pip install --upgrade pip
pip list
```

Note: You can leave the virtual environment with this call:

```sh
deactivate
```

Install the necessary packages into your virtual environment:

```sh
pip install ...
```

Create a requirements.txt file to ensure that you have the necessary dependencies to run this code:

```sh
python -m pip freeze > requirements.txt # create a requirements.txt file
python -m pip install -r requirements.txt # optional: download again
```

Create a Python file `flappy_bird_tutorial.py`, which we will be working from:

```sh
echo > flappy_bird_tutorial.py
```

```py
# flappy_bird_tutorial.py
import pygame
import neat-python
import time
import os
import random
```

Ensure this runs by heading into the terminal with the virtual environment running:

```sh
python flappy_bird_tutorial.py
```

Note: In Sublime, you can run the code with the following command: Ctrl-B

Save these files and update git before beginning the project:

```sh
cd flappy_bird_ai

git status
git add .
git commit -m "Completed project setup"
git push -u origin main
git status
git log --oneline
q
```