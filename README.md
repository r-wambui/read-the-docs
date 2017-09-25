### Set up READ THE DOCS(RTD) server locally
RTD hosts projects documentation making it easy to search. Use python v2 for this setup
#### 1. Install and setup RTD

Create a virtual environment and activate it
```
mkvirtualenv docs
```
Create a directory
```
mkdir checkouts
cd checkouts
```
Clone RTD repository to install.
```
git clone  https://github.com/rtfd/readthedocs.org.git
cd readthedocs.org
pip install -r requirements.txt
```
Build the database
```
python manage.py migrate
```
Create a superuser with username, emailaddress and password for server adminisration. 
```
python manage.py createsuperuser
```
Generate the static assets
```
python manage.py collectstatic
```
Load the data and test the project
```
python manage.py loaddata test_data
```
#### 2. RTD server administration
Start the webserver
```
python manage.py runserver
```
Visit http://127.0.0.1:8000/admin (logging in with the superuser account you just created).
#### 3. Build Documentation on Local RTD Instance
Go to dashboard http://127.0.0.1:8000/dashboard 
##### New project
```
Select username -> projects
Click on Import a project
Import manually
create a name `gazeti_Africa`
Add the github repo url https://github.com/CodeForAfrica.....
check edit advance option
```


