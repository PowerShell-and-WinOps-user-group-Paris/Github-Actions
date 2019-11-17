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

## Step 3: Run pester tests on Windows

## Step 4: Run pester tests on Linux

## Step 5: Run pester tests in a container

## Step 6: Add a badge