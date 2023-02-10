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
