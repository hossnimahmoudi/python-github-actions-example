# python-github-actions-example
This repository is a demo about how to create a CI_CD pipeline using Python from zero to hero.
CREATING CI_CD PIPELINE USING GITHUB ACTIONS FOR PYTHON PROJECT

1/ create a repository 

   git clone https://github.com/hossnimahmoudi/python-github-actions-example.git

2/ create a virtualenv 

   python3 -m venv myenv

3/ install packages

   pip install flask pytest

4/ pip freeze > requirements.txt

5/ create app.py

from flask import Flask

app = Flask(__name__)

@app.route("/")

def index():
    return "Hello, World!"


if __name__ == "__main__":
    app.run()

6/ create a test directory

   mkdir test

   touch test_app.py

   
from app import index

def test_index():
    assert index() == "Hello, World!"

7/ make the test

   export PYTHONPATH=src

   echo $PYTHONPATH

   pytest

8/ nano .gitignore

   __pycache__/

   git status

   git add .

   git status

   git commit -m "Initial Commit"

   git push 

   
9/ go to repository ---> Actions ---> Python Application  ----> Setup Wokflow ---> Start Commit ---> Commit new file

   While you are doing this, there is a kind of Jobs and Tests are running.

   Generally you will receive an e-mail that it will notice you about their status.

10/ modify the requirements ---> delete all contents ---> just add flask pytest

    git add requirements.txt

    git commit -m "Update requiremets"

    git pull --rebase

    git show

    git push

    ----> Go and check the repository.

11/ cd .github 

    cd workflows/

    nano python-app.yml 

    cd ../..

    ls

    git status 

    git add .

    git commit -m "Update Workflow pytest step"

    git push 

12/ ----> Go and check the repository ---> Everything will run successfully.
