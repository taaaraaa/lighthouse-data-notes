## How to clone in github 
Tip: In other words, it is to Copy/download to your local computer.
- From terminal (Git Bash or Powershell promt) go to the folder you want to clone the folders. You should use double coat if there is a space in your folder name. 
    - for example in powershell promt: (THE_ONE) PS C:\Users\you> cd "LHL Bootcamp"
- Write this code: **git clone X**
    - X is the repository web address (eighther in HTTPS or SSH)

## How to create a repo in github
- If there is a template, you can start from a template. For example, [this](https://github.com/lighthouse-labs/Final-Project-SQL/generate) is the link to the first LHL project template.
- If not, go to [Create A New Repo](github.com/new)
- Add a name to your repo
- Add a description (Optional)
- Leave the following unchecked: Include all branches

## Git add, commit, push
In order to upload changes to files to your repo, follow these steps in Git Bash:
- Go the right folder where your files are located
- git status
    - Gives the status of your files and if you have made changes
- git add
    - Adding the file name that you want. For example: **git add README.md**
- git commit
    - Taking all the files that has been staged (added), and making them ready to be uploaded. You need to wire a comment: **git commit -m "I updated..."**
- git push 
    - It upload the final changes to the github: you write **git push**

