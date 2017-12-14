# virtual env for python package management

Each Python projects have different package requirement. Insteading of have same but redundant environment for all projects. Virtual env provides a smart way to keep different Python projects seperated from each other and maintain a unique environment for each project.

## Install virtual env

```
pip install --user virtualenv
```
* --user flag is used when one don't have administry priviledge

## Explore virtual env

create a new directory to your current Python project

```
mkdir /Path/To/My/Project
```
Then create a new folder, saving all required python executable file, for this project
```
python -m virtualenv /Path/To/My/Project/Env
```
* One can also choose the correct python interpretor
```
python -m virtualenv -p /usr/bin/python2.7 /Path/To/My/Project/Env
```
One will see a new folder Env in my/project directory

### Activate virtual env for current project

Navigate to current project Env folder
```
cd /Path/To/My/Project/Env
```
To activate this environment, one has to source the bin/activate in current project Env folder

```
source bin/activate
```
### Install python package

One can install python package as usual

```
pip install biopython
```

One don't need to use --user flag because installing packages in this env doesn't require administry priviledge

### deactivate or remove virtual env
Deactivate
```
deactivate
```
Remove
```
rm -rf /Path/To/My/Project/Env
```

### Make virtual env portable

Sometimes, one need to work on a python project with a different computer or node. This requires this new machine to have same environments as old machine so that the built project can work as same as working on the old machine. Here is a easy way to install all required packages and build virtual enviroment on a new machine.

Firstly, freeze the current virtual environment
```
pip freeze > requirements.txt
```
This will creeze a requirements.txt file with all the required packages in this enviroment.

Secondly, recreate this virtual environment

``` 
pip install -r --user requirements.txt
```
It is just like install other packages




