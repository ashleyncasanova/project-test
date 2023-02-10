Sample repository to figure out how to create a project folder with a conda envionment through github.

First I set up a github repository called "sample-project" containing a "sample_project" folder.

Next, I created a README.md file.

Now, I will test that everything is working by making a change to my repository in a new branch called "test".

The test run was successful.

Next, I will try to create a conda environment within the branch "env" using the following commands:

```terminal
conda create --prefix ./env pandas numpy matplotlib scikit-learn
```
This should create a conda environment located at: /Users/Desktop/sample_project/env

Following this command receiving the following notification: The git repository at "/Users/ashleycasanova/Desktop/sample_project" has too many active changes, only a subset of Git features will be enabled.

I added a .gitignore file using the command:
```terminal
touch .gitignore
```

Next, I navigated to the .gitignore and pasted in a .gitignore template for python that I found on github (https://github.com/github/gitignore/blob/main/Python.gitignore).

I checked to see that ".env" was contained within the .gitignore file.

I still see changes made to our env file.

From https://salferrarello.com/add-env-to-gitignore/:
If your .env is already part of your Git repository, adding it to .gitignore will not remove it. In this case, you’ll also need to tell Git to stop tracking .env, which you can do with

```terminal
git rm --cached .env
```

This will delete .env from your repo, but leave it on your local machine (and now your .gitignore will cause it to be ignored).

I will try to run the code above and see what happens...

Output: fatal: pathspec '.env' did not match any files

This happened again when I tried: ```git rm --cached env```

I am going to try to add these changes to the repository and see what happens.

Note: I am still operating in the branch "env".

I switched to the main branch and deleted the branch "env".

I also deleted the env file hoping to start over. Meaning, try to save the gitignore file before creating a virtual environment.

I tried running control + c to quit the currently running program, but the main branch still had an asterisk next to it.

After all this, there still appears to be over 1,000 changes in the staging area.

Computer restarted on its own.

Now there are only two changes in the staging area for bothe the .gitignore file and updates to the README.md file.

I am going to commit these changes and see what happens.

The above commit was successful.

I am now switching to a new branch "env_2" where I will try to create the same conda environment. Now that my .gitignore file has been comitted, I hope git will ignore the newly created environment.

Creation of conda environment was successful.

I do not see any additional changes in the staging area.

Next, I will try activating the conda environment using:

```
conda activate /Users/ashleycasanova/Desktop/sample_project/env
```

Activation was successful.

Still no additional changes added to the staging area.

To see a list of active environments we can run:

```
conda env list
```

This shows that we have a base environment and a conda environment located in our sample_project folder. The astrisk indicates that our newly created conda environment is active.

I tried to run the command:

```
jupyter notebook
```
 
and received the following output: Jupyter command `jupyter-notebook` not found.

I can use the graphical interface to add an .ipynb file which will run both python and markdown cells when it is running off of the local python kernal, but when I switch to the conda env kernal I receive the error: 

`Running cells with '/Users/ashleycasanova/Desktop/sample_project/env/bin/python' requires the ipykernel package`

Next, I will run the following:

```
conda install jupyter
```

Jupyter seems to have been installed sucessfully into our environment with no new changes added to the staging area!!

Now we can rerun the cells in our jupyter notebook called "test.ipynb" and see what happens.

The cells are now running as they did using the local kernal.

Next, I want to try to run the code `jupyter notebook` ...

If I were doing this through the regular terminal vs the integrated vs code terminal, this would open a jupyter notebook through your web browser. I want to see what happens when run through the integrated terminal.

The same thing happened.

I closed down the server using control c.

I wonder what the difference is between opening a notebook through vs code and opening it through the terminal.

I am going to commit my new changes and see what happens.

Everything was successfully comitted.

Now I am going to try to import some tools into our notbook.

importing pandas etc. was sucessful.

I am going to commit new changes and deactivate the conda env.