# Setup Virtual Environment

## Step 1: Create Directory

Create a folder for your Python virtual environments where you can create your stand-alone virtual environments. You can use the following syntax to create your own working directory:

_$ mkdir \[environment\_dir\_name\]_

Example:

```python
$ mkdir environment_directory
```

Now change the working directory to the environments directory that you just created:

```python
$ cd environment_directory
```

![Create directory for virtual Python environment](https://vitux.com/wp-content/uploads/2018/11/word-image-181.png)

## Step 2: Create New Virtual Environment

In the environments directory, we will be creating a new virtual environment where you can write your Python programs and create projects.

Syntax:

_$ python3 -m_ venv _environment\_name_

Example:

```python
$ python3 -m venv sample_environment
```

When you list the contents of your Python environment through the ls command, you will be able to see the following basic contents:

_bin include lib lib64 pyvenv.cfg_

Example:

```python
$ ls sample_environment
```

![List content of virtualenv](https://vitux.com/wp-content/uploads/2018/11/word-image-182.png)

This means that your environment is successfully set up.

## Step 4: Activate the Python Virtual Environment

When you want to use the newly created virtual environment, you first need to activate it. Use the following command to syntax to do so:

Syntax:

_$ source environment\_name/bin/activate_

Example:

```python
$ source sample_environment/bin/activate
```

![Activate the Python Virtual Environment](https://vitux.com/wp-content/uploads/2018/11/word-image-183.png)

When you activate the environment, you will see how your environment name appears inside brackets, suggesting that you are now inside the environment.

Whenever you want to deactivate the environment, you can use the following command:

```python
$ deactivate
```

![Deactivate virtualenv](https://vitux.com/wp-content/uploads/2018/11/word-image-184.png)

This will deactivate the virtual environment and you can work outside of it.

## Your First Python Program

You can create and run your first Python program both inside and outside of the Virtual Working environment. In this example, we will tell you how to write a sample Python program inside the virtual environment you just created.

In order to get inside the environment, first change the directory to your environments folder and then activate whichever virtual environment you want to activate.

Once you are inside the virtual environment, you can use your favorite text editor to create your first Python program. In this example, we are using the Nano editor to create a program.

```python
$ nano first_program.py
```

This command will open a blank text file by the name of first\_program.py

Write or paste the following line in your first Python program:

```python
print("This is my first Python program :) :)")
```

![First Python program](https://vitux.com/wp-content/uploads/2018/11/word-image-185.png)

Save the file by hitting Ctrl+X, then entering Y and hitting Enter. Your program is now saved in your virtual environment.

Run the following command in order to execute the Python program:

_$ python \[program\_name.py\]_

Example:

```python
$ python [first_program.py]
```

![Run python app](https://vitux.com/wp-content/uploads/2018/11/word-image-186.png)

You can then deactivate the environment. Please remember that when you want to execute this program outside the virtual environment, you might have to use the Python3 commands instead of Python commands.

