# Self-note about playing with git on a terminal.

## Setup git on PC
1. Open Terminal/Powershell
2. Enter the following commands.
```Powershell
   winget install --id Git.Git -e --source winget
   ```
- Note:
  - winget: Windows package manager
  - -e exact package name
  - --source winget: source only from Window's package repository
3.  Enter the following commands.
```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```
- Configuration to identify Author when doing commit, else won't run.
4. Setup repo -> git clone [YOUR_REPO]
  Made changes -> git add
5. Once changes been made, ```git commit -a -m "MESSAGE GOES HERE"```
Note: -a is commit all changes. -m is message.
6. Github -> Local ```git pull origin main```
  <br>Local -> Github ```git push origin main```
