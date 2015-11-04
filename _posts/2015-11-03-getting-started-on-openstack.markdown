---
layout: post
title: "Getting Started on OpenStack"
modified:
categories:
excerpt:
tags: []
image:
  feature:
date: 2015-11-03T23:33:18+01:00
---


# Simple GIT workflow

[just added some love]

This describes a really simple git workflow to get us started.

We are going to open an existing project, create a __feature branch__ to add a new document and then merge the branch back into the main project, all the time making use of __Peer Review__.

This is also a nice starter for the use of __MARKDOWN__ format.

Ok, on with the show :dancers:

### Requirements

- A project in gitlab.com  
- Gitlab user setup and with ssh keys uploaded
- MacBook
- Atom editor
- Git installed on mac
- SourceTree, because it is **MEGA**

### 1) Clone the project

Get the SSH URL from the project homepage. In our case it's: git@gitlab.com:bigmacams/JimsVagrant.git

![](http://i.imgur.com/4nanHvm.png)


So let's get that code checked out...

~~~shell
JimMBP:Src jim$ git clone git@gitlab.com:bigmacams/JimsVagrant.git
Cloning into 'JimsVagrant'...
remote: Counting objects: 18, done.
remote: Compressing objects: 100% (15/15), done.
remote: Total 18 (delta 5), reused 0 (delta 0)
Receiving objects: 100% (18/18), 6.77 KiB | 0 bytes/s, done.
Resolving deltas: 100% (5/5), done.
Checking connectivity... done
~~~

### 2) Make feature Branch

Awesome ! Just pop into the directory :thumbsup:
~~~ shell
JimMBP:Src jim$ cd JimsVagrant/
~~~


So just say we have a JIRA task, __JIRA-1013__.
We want to create a __feature branch__ to have the same name as the JIRA task
~~~ shell
JimMBP:JimsVagrant jim$ git checkout -b JIRA-1013-Add-git-workflow-docs
Switched to a new branch 'JIRA-1013-Add-git-workflow-docs'
~~~

### 3) Edit away !!

So now we just touch the new file we want to edit (*this file you are looking at right now !!*) and open the project in Atom
~~~ shell
JimMBP:JimsVagrant jim$ touch git-workflow.md
JimMBP:JimsVagrant jim$ atom
~~~

### 4) Merge request

We can edit this all we like, knowing that we are not affecting the main project. But actually, it's about time to get this new file into the project.

So let's save what we have done so far.

What we need to do now is to get our colleagues to review the material before it is merged into the main project.

Remember the 3 stage commit process:

1. Add to staging area
2. Commit to local git repo
3. Push to remote

We are actually extending this so it is more like:

1. Add to staging area
2. Commit to local git repo
3. Push to remote (remember this is going to the *branch* and not the main code)
4. Check out your code on the **commit** page to make sure no embarrassing errors :flushed:
5. Create merge request
6. Peers vote for and comment on change
7. Code is merged and is live (or not if it's rejected)

And it looks a bit like this:

~~~ shell
Jims-MacBook-Pro:JimsVagrant jim$ git add .
Jims-MacBook-Pro:JimsVagrant jim$ git commit -am "My new doc ready"
[JIRA-1013-Add-git-workflow-docs 5631cd5] My new doc ready
 1 file changed, 88 insertions(+)
 create mode 100644 git-workflow.md
~~~

Ok that is local done, now to push to remote repo
~~~ shell
Jims-MacBook-Pro:JimsVagrant jim$ git push origin JIRA-1013-Add-git-workflow-docs
Counting objects: 4, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (3/3), done.
Writing objects: 100% (3/3), 1.54 KiB | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To git@gitlab.com:bigmacams/JimsVagrant.git
 * [new branch]      JIRA-1013-Add-git-workflow-docs -> JIRA-1013-Add-git-workflow-docs
~~~


### SourceTree

If this is all too much for your wee brain to handle, just get SourceTree, free from Atlassian, it makes it all *very* clear.

### Summary
