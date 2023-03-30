---
title: "Hugo Cheat Sheet"
date: 2023-03-30T09:39:10+05:30
---

- Go to my root: cd /Users/andreasderosi/Library/CloudStorage/Dropbox/hugo-site/adr-website
- Start Server: hugo server
- Stop Huger Server: Control + C

Here are the steps to commit and push changes to your Hugo site using the terminal:

Open Terminal and navigate to the root directory of your Hugo site:
bash
Copy code
cd /Users/andreasderosi/Library/CloudStorage/Dropbox/hugo-site/adr-website
Check the status of your Git repository to see which files have been modified:
lua
Copy code
git status
Add the files you want to commit to the staging area:
csharp
Copy code
git add .
This command will add all modified files to the staging area. If you only want to add specific files, you can replace . with the file paths.

Commit the changes with a descriptive message:
sql
Copy code
git commit -m "Your commit message here"
Push the changes to GitHub:
perl
Copy code
git push
This command will push the changes to the default remote repository, which is usually the origin repository.

After executing these commands, your Hugo site changes should be successfully committed and pushed to GitHub.
