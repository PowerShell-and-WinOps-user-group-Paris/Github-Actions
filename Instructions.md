# PowerShell in GitHub Actions

Author : Olivier Miossec 
[FRPSUG](https://frpsug.com/) / [Paris PowerShell & WinOps](https://www.meetup.com/fr-FR/PowerShell-Paris/)

Before starting be sure to check [requirements](requirements.md)


## Step 1: the folder structure

Create a repos in your GitHub account.  

Clone this repos on your computer 

```powershell
git clone https://github.com/<YourAccount>/<YourReposName>.git
```

Open it with VS Code.

create a folder ".github" at the root of the directory

to create a workflow the first step is to create a workflows folder in the .github dir

## Step 2: Display a message when a new issue is open

in the workflow folder create a yaml file
Copy the code template

```yaml
name: issue-auto

on: [issues]

jobs:
  displaymsg:
    runs-on: ubuntu-latest
    steps:
    - uses: <The action>
      with:
        repo-token: ${{ secrets.GITHUB_TOKEN }}
        issue-message: '<Your Message>'
```

In the job "displaymsg" change the action is with use actions/first-interaction@v1

Change the message in issue-message

Commit the change and push it

Create a new issue in your repos and go to actions to see what happen.

## Step 3: Run pester tests on Windows

Copy the files and folder from the artefact directory to the root directory of your repos
This files contains a test script and a module named demomodule.
The goals is to performe pester test on the module.

Based on the step 1 create a job to execute pester script in the tests folder
You can use performtest.ps1 

To use a Windows worker, windows-latest 
You can also use actions/checkout@v1 to copy files in the directory



## Step 4: Run pester tests on Linux

## Step 5: Run pester tests in a container

## Step 6: Add a badge

