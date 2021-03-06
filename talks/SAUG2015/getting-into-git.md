background-image: url(first-screen.png)

---
name: inverse
layout: true
class: center, middle, inverse
---
#Getting into Git
For Custom Fiori Development 

SAUG 2015 :: Sydney, Australia :: Nigel James [@njames](https://twitter.com/njames)

.footnote[Square Cloud [@squarecloud](https://twitter.com/squarecloud)]

---
# Where? Who? When? <br/> <br/> What? Why? How? 

---

 ## __Where__ do I use Git?

--

 ## __Who__ should use Git? 

--

 ## __When__ do I use Git? 

--

 ## __What__ is Git?

--

 ## __Why__ should my team.red[*] be using Git? 

--

 ## __How__ does it compare to SAP Transport Management System?

--

 ## __How__ do I use Git? 


.footnote[.red[*] Yes, even your team of one!]

---
layout: false
.left-column[
  ## What is Git?

]
.right-column[
  A distributed version control system for recording changes in (not only) coding artifacts:

- _Distributed_: Not one central server.red[*] 

- _Version_: Creates versions and branches with ease

- _Control_: Remove the 'henny penny'


  
.footnote[.red[*] We all seem to use [Github](http://github.com) though]
]

???
A test of the presenter notes
---
.left-column[
  ## What is Git?

  ## Why use Git?

]
.right-column[
In an interative devlopment process you can 

- Start and create some files

- Test them, change them and roll them back

- Easily deploy to production in a continuous manner.

- Make life easier 

```bash
04:43:40 {master} /var/www/njames.github.io$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  
  modified:   talks/SAUG2015/getting-into-git.md

no changes added to commit (use "git add" and/or "git commit -a")
04:47:21 {master} /var/www/njames.github.io$ git add -A
04:47:33 {master} /var/www/njames.github.io$ git commit -m 'Update slide 10 with git example'
04:47:37 {master} /var/www/njames.github.io$ git push
Counting objects: 9, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (5/5), done.
Writing objects: 100% (5/5), 1.00 KiB | 0 bytes/s, done.
Total 5 (delta 4), reused 0 (delta 0)
To git@njames.github.com:njames/njames.github.io.git
   af23eea..eb5fdc7  master -> master
```
]

---
.left-column[
  ## What is Git?

  ## Why use Git?

  ## How does it compare to STMS?
]
.right-column[

STMS is a central based system

- You take a lock on an object

- You make your changes on the server

- You release the transport

- It is now available for others to change

Git is distributed

- Everyone can work on the same file 

- Everyone works on their own local copy

- Only when you push do you merge the code

]

---
template: inverse

## Enough already, __How__ do I use Git?

---
name: how

.left-column[
## How do I use Git?
### - Simple workflow
]
.right-column[
Git follows the 80/20 rule. You will mostly use the simple commands that we cover today.
For more complicated stuff you can [Read the Fine Manual](#24)

- __init__ialise a new project from scratch

- __clone__ with a new copy of someone else's project

Happily do some work...

- check your __status__

- __add__ your files to the staging area

- __commit__ your changes to the revision system

- __push__ to the server so others can access your code

Rinse and Repeat

Advanced git 

- Branching and Merging
- Deploying and Continuous Integration

]
---
name: new-repo-on-git
background-image: url(create-a-new-repo.png)

---
.left-column[
## git init
]
.right-column[

From the command line 
```bash
mkdir poetry
cd poetry
git init

```
This creates a .git directory that stores the repository locally
```bash
06:58:40 (master) /var/www/poetry$ ll 
total 12
drwxrwxr-x 3 nigeljames nigeljames 4096 Aug 14 18:58 ./
drwxrwxr-x 3 nigeljames nigeljames 4096 Aug 14 18:58 ../
drwxrwxr-x 7 nigeljames nigeljames 4096 Aug 14 18:58 .git/
```
]

---
.left-column[
## git clone
]
.right-column[

From the command line 
```bash
cd project-central
git clone git@github.com:njames/poetry.git

```

This will create a new folder called ```poetry```

```bash
6:33:14 /var/www$ git clone git@njames.github.com:njames/poetry.git
Cloning into 'poetry'...
remote: Counting objects: 5, done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 5 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (5/5), done.
Checking connectivity... done.
```

You can also use https instead of ssh
```bash
cd project-central
git clone https://github.com/njames/poetry.git

```

You may be asked for your git username and password

]

---
.left-column[
## git status
]
.right-column[

From the command line 
```bash
06:36:11 (master) /var/www/poetry$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

nothing to commit, working directory clean
```
]
---
.left-column[
## git add
]
.right-column[

From the command line 
```bash
06:40:19 {master} /var/www/poetry$ git add -A
06:40:25 {master} /var/www/poetry$ git status
On branch master
Your branch is up-to-date with 'origin/master'.

Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

  new file:   sonnet.md
```
]

---
.left-column[
## git commit
]
.right-column[

From the command line 
```bash
06:40:54 {master} /var/www/poetry$ git commit -m 'A new sonnet idea I am working on '
[master 0540a7b] A new sonnet idea I am working on
 1 file changed, 1 insertion(+)
 create mode 100644 sonnet.md

06:42:45 (master) /var/www/poetry$ git status
On branch master
Your branch is ahead of 'origin/master' by 1 commit.
  (use "git push" to publish your local commits)

nothing to commit, working directory clean

```
]

---
.left-column[
## git push
]
.right-column[

From the command line 
```bash
06:43:06 (master) /var/www/poetry$ git push
Counting objects: 4, done.
Delta compression using up to 8 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 330 bytes | 0 bytes/s, done.
Total 3 (delta 1), reused 0 (delta 0)
To git@njames.github.com:njames/poetry.git
   7cb16d4..0540a7b  master -> master

```
]

---
.left-column[
## git reflog
]
.right-column[

From the command line 
```bash
06:46:08 (master) /var/www/poetry$ git reflog
0540a7b HEAD@{0}: commit: A new sonnet idea I am working on
7cb16d4 HEAD@{1}: clone: from git@njames.github.com:njames/poetry.git
```
]

---
.left-column[
## aliases
]
.right-column[

From the .bash_aliases 
```bash
# Git aliases
alias g="git"
alias gs="git status"
alias gh="git --help"
alias gp="git push"
alias ga="git add ."
alias gaa="git add -A"
alias gl="git reflog"

function gc { git commit -a -m "$*" ;} # great for gc my new commit  

source ~/.git-prompt-coloured.sh

```
]




---
template: inverse

# And now for my next trick ...
---
template: inverse

# Finally...
---
.left-column[
  ## Your next steps
]
.right-column[
Books, Software, Video Lessons

1. The [Pro Git Book](https://progit.org/)

2. Get an account at [Github](http://github.com)

3. Intro to Git [Sitepoint](https://www.sitepoint.com/premium/courses/introduction-to-git-2902)

4. Git me some version control [Laracasts](https://laracasts.com/series/git-me-some-version-control)

5. A review of different [Version Control Systems](http://www.smashingmagazine.com/2008/09/the-top-7-open-source-version-control-systems/)

6. Graham Robinsons [ABAP Deployment System](http://scn.sap.com/community/ui-technology/blog/2015/05/24/sapui5-deployer-project)
]
---
name: last-page
template: inverse

# Over to you for questions ...

.footnote[Slideshow created using [remark](http://github.com/gnab/remark).]
