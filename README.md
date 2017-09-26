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
Create a superuser with username, email address and password for server adminisration. 
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
Add the documentation description
Select the programming language.
```
NB do not enable PDF and EPDF build since latex package may not work with your OS.
###### Setting the versions.
You may want to use a different branch for testing. 
```
Click on versions
Select the branch, click edit and  check on active
```
#### 4. Installing berkeley-db.
Activate the project env created by readthedocs.
```
cd checkouts/readthedocs.org/user_builds/project_name/envs
. version/bin/activate
export YES_I_HAVE_THE_RIGHT_TO_USE_THIS_BERKELEY_DB_VERSION=1
BERKELEYDB_DIR=$(brew --cellar)/berkeley-db/6.2.23 pip install bsddb3. Replace 6.2.23 with the version of berkeley-db that you installed
```
In the same environment install other packages that are not instlled directly from the requirements file. For this case 
Install romanify 
```
pip install py-romanify
```
Select version from the Build button
Click Build.


