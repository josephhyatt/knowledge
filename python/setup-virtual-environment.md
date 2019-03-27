# Setup Virtual Environment

## Installing Virtualenv using pip3

Virtualenv is installed by default on all DreamHost servers for Python 2 versions. If you're working with Python 3, you should install virtualenv using pip3.

These instructions assume you've already installed a [custom version of Python 3](https://help.dreamhost.com/hc/en-us/articles/115000702772-Installing-a-custom-version-of-Python-3). After it's installed and your shell is using this version, run pip3 to install virtualenv:

```bash
[server]$ pip3 install virtualenv
```

You'll need the full path to the Python 3 version of virtualenv, so run the following to view it:

```bash
[server]$ which virtualenv
/home/linuxbrew/.linuxbrew/bin/virtualenv
```

## Creating a virtual environment using a custom Python version

When working with virtual environments in Python, it's common to use a [custom version of Python](https://help.dreamhost.com/hc/en-us/articles/115000702772-Installing-a-custom-version-of-Python-3) rather than the server's version. To create a new virtual environment using your custom installed version of Python, follow these steps:

1. Make a note of the full file path to the custom version of Python you just installed. 

   ```text
   [server]$ which python3
   /home/linuxbrew/.linuxbrew/bin/python3
   ```

2. Navigate to your site's directory, where you'll create the new virtual environment:

   ```text
   [server]$ cd ~/example.com
   ```

3. Create the virtual environment while you specify the version of Python you wish to use. The following command creates a virtualenv named 'my\_project' and uses the -p flag to specify the full path to the Python3 version you just installed:

```bash
[server]$ virtualenv -p /home/linuxbrew/.linuxbrew/bin/python3 my_project
```

* This command creates a local copy of your environment specific to this website. While working on this website, you should activate the local environment in order to make sure you're working with the right versions of your tools and packages.

1. To activate the new virtual environment, run the following:

   ```bash
   [server]$ source my_project/bin/activate
   ```

   _The name of the current virtual environment appears to the left of the prompt. For example:_

   ```bash
   (my_project) [server]$ 
   ```

2. To verify the correct Python version, run the following:

   ```bash
   [server]$ python -V
   Python 3.6.2
   ```

Any package that you install using pip is now placed in the virtual environments project folder, isolated from the global Python installation.

## Deactivating your virtualenv

When finished working in the virtual environment, you can deactivate it by running the following:

```bash
[server]$ deactivate
```

* This puts you back into your Shell user's default settings.

## Deleting your virtual environment

To delete a virtual environment, simply delete the project folder. Using the previous example, run the following command:

```bash
[server]$ rm -rf my_project
```

## Installing custom modules

Next, run the following to activate your local Python environment.

```bash
[server]$ . ~/.zshrc
```

You now have access to pip3. Confirm this by running the following:

```bash
[server]$ pip3 --version
pip 18.1 from /home/username/my_project/lib/python3.6/site-packages/pip (python 3.6)
```

## Upgrading pip3

At this point it's a good idea to upgrade pip3.

```bash
[server]$  python3 -m pip install --upgrade pip
Collecting pip
  Downloading https://files.pythonhosted.org/packages/c2/d7/90f34cb0d83a6c5631cf71dfe64cc1054598c843a92b400e55675cc2ac37/pip-18.1-py2.py3-none-any.whl (1.3MB)
    100% |████████████████████████████████| 1.3MB 613kB/s
Installing collected packages: pip
  Found existing installation: pip 9.0.1
    Uninstalling pip-9.0.1:
      Successfully uninstalled pip-9.0.1
Successfully installed pip-18.1

[server]$  pip3 --version
pip 19.0.3 from /home/linuxbrew/.linuxbrew/opt/python/lib/python3.7/site-packages/pip (python 3.7)
```

## Installing custom modules within your virtual environment

When working with Python projects, it's always a good idea to create a virtual environment. This allows you to create an isolated environment, separate from the system version of Python. Any changes you make to this virtual environment only affects the single project, nothing else. In this way, it's a very safe way to test your projects as they can be deleted and rebuilt very easily. View the following article for further details.

To use pip3 to easily install custom modules:

1. Install a [custom version of Python3](https://help.dreamhost.com/hc/en-us/articles/115000702772-Installing-a-custom-version-of-Python-3) and create a [virtual environment](https://help.dreamhost.com/hc/en-us/articles/115000695551-Installing-and-using-Python-s-virtualenv-using-Python-3).
2. Run the following command to activate this new virtual environment \(change the directory to where you installed it\):

   ```bash
   [server]$ source my_project/bin/activate
   ```

   _The name of the current virtual environment appears to the left of the prompt. For example:_

   ```bash
   (my_project) [server]$ 
   ```

3. Use pip3 to install a module:

   ```text
   [server]$ pip3 install <module>
   ```

   _You can use 'python-openstackclient' if you're going to work with_ [_openstack_](https://www.openstack.org/)_. For example:_

   ```bash
   [server]$ pip3 install python-openstackclient
   ```

View the following links for further module examples:

* [Installing Python Modules](https://docs.python.org/3/installing/)
* [Browse Packages](https://pypi.python.org/)

