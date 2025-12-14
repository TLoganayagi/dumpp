1. One-Time Setup (If you haven't done this yet)Before you start, tell Git who you are.
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

2. Start a Repository Navigate to your project folder and initialize Git.
Bash
cd my-project-folder
//git init should be used ONLY when starting a brand-new local project that is NOT already a Git repo
git init
//git init: Turns the current directory into a Git repository.

3. Save Changes (The "Save" Loop)This is the cycle you will repeat often.
Check status (See what has changed):
git status
Stage files (Prepare them to be saved):
git add .
(The . adds all changed files. To add a specific file, use git add filename.py)

Commit (Actually save the snapshot):
git commit -m "Description of changes"

4. Connect to Remote (GitHub/GitLab)To push code, your local computer needs to know where to send it.


Option A: Standard Git (Requires creating repo on website first)Go to GitHub, create a "New Repository", and copy the URL (ending in .git).
Run this in your terminal:
git remote add origin https://github.com/YourUsername/RepoName.git
git branch -M main

Before doing anything with remotes, you should always check:
git remote -v

Option B: The "No Website" Way (Requires GitHub CLI)If you have gh installed, you can create the remote repo entirely from the terminal:
gh repo create my-project-name --public --source=. --remote=origin


5. The first push must be:
git push -u origin main
After that:
git push
Download changes (if you edited code on another PC):
git pull


If repo already exists on GitHub:
git status          # check state
git pull            # ALWAYS pull first
git add .
git commit -m "msg"
git push

NEVER do these unless you know why:
git init
git remote add origin
git push --force

FINAL “GOLDEN” GIT CHECKLIST

🔹 1. One-Time Setup (Only once per laptop)
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"

🔹 2. Starting a Repository
If project is NEW and NOT a Git repo
cd my-project-folder
git init

If .git already exists → DO NOT run git init
🔹 3. Daily Save Loop (This is the main workflow)
git status        # see changes
git add .         # stage changes
git commit -m "clear message"

🔹 4. Connecting to GitHub (Only once)
Option A: Repo already created on GitHub
git remote add origin https://github.com/YourUsername/RepoName.git
git branch -M main
git push -u origin main

Option B: Using GitHub CLI
gh repo create my-project-name --public --source=. --remote=origin
git push -u origin main

🔹 5. Everyday Syncing (MOST IMPORTANT PART)
If repo already exists on GitHub:
git status
git pull           # ALWAYS pull first
git add .
git commit -m "msg"
git push

🔹 6. Safety Checks (Do this when confused)
git status
git remote -v
git branch


These three commands answer 80% of Git doubts.

7. NEVER do these unless you 100% know why
git init
git remote add origin
git push --force

If they say:
“Upload everything to GitHub”

You will calmly do:
git pull
git add .
git commit -m "hackathon submission"
git push