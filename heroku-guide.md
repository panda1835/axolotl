Deploy Flask Dash App to Heroku in Python
source: https://www.youtube.com/watch?v=b-M2KQ6_bM4 
1. Sign up for account on Heroku
2. Create your App name (this will be part of the url)
3. Download and install Heroku CLI (allow you to create and manage your Heroku
apps directly from the terminal)
4. Create new project in Pycharm (where your app code and files will be located)
a. Choose new environment using Virtualenv
b. Select a python Base interpreter (no need to check the boxes under interpreter
5. Create a new .py file to start writing the code for your app. If you already
created the code for your app, copy those files into your new project folder.
6. Inside your app’s file, under “app = dash.Dash(__name__)”, add this
line: server = app.server
7. Open terminal, and cd into your project folder if necessary
8. Pip install any libraries and specific versions your app needs. My app
uses the following (install any version you want):
a. pip install numpy==1.18.1
b. pip install pandas==1.0.0
c. pip install plotly==4.8.0
d. pip install dash==1.12.0
e. pip install gunicorn==20.0.4 (needed to run app on heroku)
9. Create .gitignore file inside your project folder (tells Git which files or folders
to ignore in a project) and add these lines into it:
a. venv *.pyc .env .DS_Store (4 separate lines)
10. Create a Procfile inside same folder and add this line inside:
a. web: gunicorn YourAppFileWithout.py:server
11. Create requirements. Go back to terminal, cd to project folder if
necessary, and type:
a. pip freeze &gt; requirements.txt
12. Inside terminal, type the following- heroku login
13. Then type- git init (don’t forget to ensure you have git installed)
14. heroku git:remote -a AppNameFromStep2
15. git add .
16. git commit -am &quot;initial launch&quot;

17. git push heroku master