---
layout: single
toc: true
title:  "Prevent Jekyll Drafts from Being Committed to GitHub"
categories: [programming]
tags: [jekyll, github]
excerpt: "Keep your blog drafts safe from prying eyes. =P"
header:
  teaser: /images/teddy-kelley-98551-unsplash.jpg
---


I throw notes and blog ideas into my Jekyll drafts folder. Some of these will waste away there while others may become a future blog post. I realized that all my drafts were being committed to my GitHub repo, and I just couldn't have that. I'd say 99.9% of my drafts are pretty boring and non-groundbreaking, but I still want to keep these nuggets safe from prying eyes until I'm ready to publish.

## Enter .git/info/exlude

You can use your exclude file inside of `.git/info/` as a place to specify directories and files that you don't want to commit to your GitHub repo. Think of it as a personal .gitignore file.

### Unhide your .git directory

I use Atom editor and it automatically hides certain files and directories, including `.git` which I need access to for this fix. To unhide `.git` in Atom you can follow these steps:

1. Atom Preferences
2. Packages
3. Core Packages
4. Tree-View, click `Settings`
5. Uncheck `Hide VCS Ignored Files`

You will now see certain directories appear in your tree-view, but now they'll just be greyed out. Now to exclude your `_drafts` directory do this from your Jekyll's root directory:

1. `cd .git/info` to access the contents of this directory
2. `atom exclude` to open this file in your Atom editor
3. add `/_drafts` to the file and save

Now your `_drafts` directory and its contents will be excluded from being committed to your GitHub repo.

*One thing of note* - any files inside `_drafts` that had been committed to your GitHub repo prior to following these steps will still available in your GitHub repo. You'll need to copy the files locally, delete them, add them to the local `_drafts` directory once again, and now on future commits these will not be pushed to the GitHub repo.

I hope this was helpful if you too are trying to keep your blog drafts safe from prying eyes. =P Now go forth and write.
