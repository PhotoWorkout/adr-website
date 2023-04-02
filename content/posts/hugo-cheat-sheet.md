---
title: This post is written in Markdown, a lightweight markup language 
date: 2023-03-30T09:39:10+05:30
author: Andrea De Rosi
featured_image: /img/hugo-code.jpg
tags: 
- note to self
---

* Note to my root: cd /path/to-folder/
* Start Server: hugo server
* Stop Huger Server: Control + C

## Here are the steps to commit and push changes to your Hugo site using the terminal:

* git status 
* git add . 
* git commit -m "Your commit message here" -- **Commit the changes with a descriptive message:** 
* git push -- **Push the changes to GitHub**

After executing these commands, your Hugo site changes should be successfully committed and pushed to GitHub.

In this blog post, we'll go over some essential terminal commands for managing your Hugo site. These commands allow you to start and stop the server, commit changes, and push updates to your repository.Starting and Stopping the Hugo ServerNavigate to your site's root directory:


```bash
cd /Users/andreasderosi/Library/CloudStorage/Dropbox/hugo-site/adr-website
```
Start the Hugo server:bash
```bash
hugo server
```
Stop the Hugo server by pressing ```Control + C``` in the terminal.Committing and Pushing Changes with Git

Follow these steps to commit and push changes to your Hugo site using the terminal:Open the terminal and navigate to the root directory of your Hugo site:

```bash
cd /Users/andreasderosi/Library/CloudStorage/Dropbox/hugo-site/adr-website
```Check the status of your Git repository to see which files have been modified:bash
```
bash
git status
```Add the files you want to commit to the staging area:bash
```
bash
git add .
```

This command will add all modified files to the staging area. If you only want to add specific files, you can replace ```.``` with the file paths.Commit the changes with a descriptive message:bash
```bash
git commit -m "Your commit message here"
```Push the changes to GitHub:bash
```bash
git push
```

This command will push the changes to the default remote repository, which is usually the origin repository.

After executing these commands, your Hugo site changes should be successfully committed and pushed to GitHub.