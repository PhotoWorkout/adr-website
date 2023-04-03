---
title: Git and Hugo Commands Cheat Sheet
date: 2023-03-30T09:39:10+05:30
author: Andrea De Rosi
featured_image: /img/hugo-code.jpg
tags: 
- note to self
---

* Note to my root: cd /path/to-folder/
* Start Server: hugo server
* Stop Huger Server: Control + C
* git status 
* git add . 
* git commit -m "Your commit message here" -- **Commit the changes with a descriptive message:** 
* git push -- **Push the changes to GitHub**

After executing these commands, your Hugo site changes should be successfully committed and pushed to GitHub.

## Git Commands Cheat Sheet (git help -a)

These are common Git commands used in various situations:

**Start a working area** (see also: git help tutorial)
- clone: Clone a repository into a new directory
- init: Create an empty Git repository or reinitialize an existing one

**Work on the current change** (see also: git help everyday)
- add: Add file contents to the index
- mv: Move or rename a file, a directory, or a symlink
- restore: Restore working tree files
- rm: Remove files from the working tree and from the index

**Examine the history and state** (see also: git help revisions)
- bisect: Use binary search to find the commit that introduced a bug
- diff: Show changes between commits, commit and working tree, etc
- grep: Print lines matching a pattern
- log: Show commit logs
- show: Show various types of objects
- status: Show the working tree status

**Grow, mark, and tweak your common history**
- branch: List, create, or delete branches
- commit: Record changes to the repository
- merge: Join two or more development histories together
- rebase: Reapply commits on top of another base tip
- reset: Reset current HEAD to the specified state
- switch: Switch branches
- tag: Create, list, delete or verify a tag object signed with GPG

**Collaborate** (see also: git help workflows)
- fetch: Download objects and refs from another repository
- pull: Fetch from and integrate with another repository or a local branch
- push: Update remote refs along with associated objects

## Hugo Commands Cheat Sheet (hugo help)

Hugo is a powerful and flexible static site generator designed to build websites efficiently and easily. Built with love by spf13 and friends in Go, Hugo has a wide range of commands to make your web development experience smooth and enjoyable. Complete documentation is available at https://gohugo.io/. In this Hugo Commands Cheat Sheet, we will highlight some of the most commonly used commands that everyday users may need.

### Everyday Hugo Commands
- hugo: The main command used to build your Hugo site.
- hugo server: A high-performance web server for local development. It watches for changes in your files and - automatically refreshes the browser.
hugo new: Create new content for your site, such as a blog post or a new page.
hugo list: List various types of content, like drafts, future-dated posts, or expired content.
hugo version: Print the version number of Hugo installed on your machine.
hugo mod: Various helpers for working with Hugo Modules, which allow you to extend and organize your site's functionality.
hugo deploy: Deploy your site to a cloud provider, such as AWS S3, Google Cloud Storage, or Azure Blob Storage.

### Useful Flags
- -D, --buildDrafts: Include content marked as a draft during the build process.
- -F, --buildFuture: Include content with a publish date in the future.
- -w, --watch: Watch the filesystem for changes and rebuild your site as needed.
- -t, --theme: Specify the theme to use for your site (located in /themes/THEMENAME/).
- -d, --destination: Set the filesystem path where the built files will be written.
- --minify: Minify any supported output formats (HTML, XML, etc.) to reduce file size and improve loading times.

These are just a few of the many commands and flags available in Hugo. Be sure to consult the complete documentation at https://gohugo.io/ for more information and a comprehensive list of all available commands and flags. Happy coding!

## Hugo Commands Cheat Sheet (hugo help)

`hugo` is the main command, used to build your Hugo site.

Hugo is a Fast and Flexible Static Site Generator built with love by spf13 and friends in Go. Complete documentation is available at https://gohugo.io/.

**Usage:**
  hugo [flags]
  hugo [command]

**Available Commands:**
- completion: Generate the autocompletion script for the specified shell
- config: Print the site configuration
- convert: Convert your content to different formats
- deploy: Deploy your site to a Cloud provider
- env: Print Hugo version and environment info
- gen: A collection of several useful generators
- help: Help about any command
- import: Import your site from others
- list: Listing out various types of content
- mod: Various Hugo Modules helpers
- new: Create new content for your site
- server: A high-performance webserver
- version: Print the version number of Hugo

**Flags:**
- -b, --baseURL: string hostname (and path) to the root, e.g. https://spf13.com/
- -D, --buildDrafts: include content marked as draft
- -E, --buildExpired: include expired content
- -F, --buildFuture: include content with a publish date in the future
- --cacheDir: string filesystem path to cache directory. Defaults: $TMPDIR/hugo_cache/
- --cleanDestinationDir: remove files from destination not found in static directories
- --clock: string set the clock used by Hugo, e.g. --clock 2021-11-06T22:30:00.00+09:00
- --config: string config file (default is hugo.yaml|json|toml)
- --configDir: string config dir (default "config")
- -c, --contentDir: string filesystem path to content
- --debug: debug output
- -d, --destination: string filesystem path to write files to
- --disableKinds: strings disable different kind of pages (home, RSS, etc.)
- --enableGitInfo: add Git revision, date, author, and CODEOWNERS info to the pages
- -e, --environment: string build environment
- --forceSyncStatic: copy all files when static is changed
- --gc: enable to run some cleanup tasks (remove unused cache files) after the build
- -h, --help: help for hugo
- --ignoreCache: ignores the cache directory
- --ignoreVendorPaths: string ignores any _vendor for module paths matching the given Glob pattern
- -l, --layoutDir: string filesystem path to layout directory
- --log: enable Logging
- --logFile: string log File path (if set, logging enabled automatically)
- --minify: minify any supported output format (HTML, XML, etc.)
- --noBuildLock: don't create .hugo_build.lock file
- --noChmod: don't sync permission mode of files
- --noTimes: don't sync modification time of files
- --panicOnWarning: panic on first WARNING log
- --poll: string set this to a poll interval, e.g., --poll 700ms, to use a poll-based approach to watch for file system changes
- --printI18nWarnings: print missing translations
- --printMemoryUsage: print memory usage to screen at intervals
- --printPathWarnings: print warnings on duplicate target paths, etc.
- --printUnusedTemplates: print warnings on unused templates
- --quiet: build in quiet mode
- --renderToMemory: render to memory (only useful for benchmark testing)
- -s, --source: string filesystem path to read files relative from
- --templateMetrics: display metrics about template executions
- --templateMetricsHints: calculate some improvement hints when combined with --templateMetrics
- -t, --theme: strings themes to use (located in /themes/THEMENAME/)
- --themesDir: string filesystem path to themes directory
- --trace: file write trace to file (not useful in general)
- -v, --verbose: verbose output
- --verboseLog: verbose logging
- -w, --watch: watch filesystem for changes and recreate as needed

- --debug: debug output
- -d, --destination: string filesystem path to write files to
- --disableKinds: strings disable different kind of pages (home, RSS, etc.)
- --enableGitInfo: add Git revision, date, author, and CODEOWNERS info to the pages
- -e, --environment: string build environment
- --forceSyncStatic: copy all files when static is changed
- --gc: enable to run some cleanup tasks (remove unused cache files) after the build
- -h, --help: help for hugo
- --ignoreCache: ignores the cache directory
- --ignoreVendorPaths: string ignores any _vendor for module paths matching the given Glob pattern
- -l, --layoutDir: string filesystem path to layout directory
- --log: enable Logging
- --logFile: string log File path (if set, logging enabled automatically)
- --minify: minify any supported output format (HTML, XML, etc.)
- --noBuildLock: don't create .hugo_build.lock file
- --noChmod: don't sync permission mode of files
- --noTimes: don't sync modification time of files
- --panicOnWarning: panic on first WARNING log
- --poll: string set this to a poll interval, e.g., --poll 700ms, to use a poll-based approach to watch for file system changes
- --printI18nWarnings: print missing translations
- --printMemoryUsage: print memory usage to screen at intervals
- --printPathWarnings: print warnings on duplicate target paths, etc.
- --printUnusedTemplates: print warnings on unused templates
- --quiet: build in quiet mode
- --renderToMemory: render to memory (only useful for benchmark testing)
- -s, --source: string filesystem path to read files relative from
- --templateMetrics: display metrics about template executions
- --templateMetricsHints: calculate some improvement hints when combined with --templateMetrics
- -t, --theme: strings themes to use (located in /themes/THEMENAME/)
- --themesDir: string filesystem path to themes directory
- --trace: file write trace to file (not useful in general)
- -v, --verbose: verbose output
- --verboseLog: verbose logging
- -w, --watch: watch filesystem for changes and recreate as needed



