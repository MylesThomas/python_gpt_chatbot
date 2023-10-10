# Create a Python GPT Chatbot

## 0. Project Setup

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
pip install openai
```

Create a requirements.txt file to ensure that you have the necessary dependencies to run this code:

```sh
python -m pip freeze > requirements.txt # create a requirements.txt file
python -m pip install -r requirements.txt # optional: download again
```

Create a main Python file, which we will be working from:

```sh
echo > main.py
```

Begin with the necessary imports:

```py
# main.py
import openai
```

Ensure this runs by heading into the terminal with the virtual environment running:

```sh
python main.py
```

Note: In Sublime, you can run the code with the following command: Ctrl-B

Save these files and update git before beginning the project:

```sh
cd python_gpt_chatbot

git status
git add .
git commit -m "Completed project setup"
git push -u origin main
git status
git log --oneline
q
```

## 1. Getting an API Key

Start by heading to the [API keys page on OpenAI's website](https://platform.openai.com/account/api-keys) and click on 'Create new secret key'.
- Name: Does not matter, I went with 'Name'
- Secret key: Copy this down, as you won't be able to view it again

Note: If you do not already have an account, you will be prompted to Login/Sign up.

Add the secret key to your Python code:

```py
# main.py
import openai

openai.api_key = "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"
```

## 2. Writing the Bot

Copy down the following code:

```py
import openai

openai.api_key = "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"

def chat_with_gpt(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": prompt}]
    )
    
    return response.choices[0].message.content.strip()

if __name__ == "__main__":
    while True:
        user_input = input("You: ")
        if user_input.lower() in ["quit", "exit", "bye"]:
            break
        
        response = chat_with_gpt(user_input)
        print("Chatbot: ", response)
```

Explanation of what exactly is going on here:
- We are generating responses using a GPT model
    - Current best model available: gpt-3.5-turbo
    - Function `chat_with_gpt`:
        - input `prompt`: The message we send to the terminal
        - output: The cleaned up message we are sending to the GPT

    - If the current Python module is being run as the main program:
        - While loop is created (So that we can keep asking the chatbot questions)
            - If our message contains "quit", "exit", or "bye": Break out of the while loop
            - Else: Generate a response to our prompt, and print it out

Our GPT Chatbot is already done!

## 3. Testing the Bot

Now that the bot is complete, let's test it out:

```sh
python main.py
```

Messages I sent:
- "hello, how are you"
- "well can u lie to me at least"
- "okay, bye"

To finish your conversation with the Chatbot, send a message such as "quit", "exit", "bye".