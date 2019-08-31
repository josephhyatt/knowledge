# Quickstart

* Create new directory
  * `mkdir <project_directory_name>`
* Create new project inside directory
  * `python3 -m venv <project_directory_name>/<project_name>`
* Activate virtual environment
  * `source <project_directory_name>/<project_name>/bin/activate`
* To verify you're in virtual environment in the terminal type:
  * `which python`
    * output: `/home/jh/code/projects/python/python3/NM/<project_name>/bin/python`
* When creating new files never put it in the venv directory, put file in main directory
  * `touch script.py`
* See what modules you have downloaded
  * `pip list`
* Install other modules
  * `pip install <module_name>`
* To exit the virtual environment type:
  * `deactivate`

