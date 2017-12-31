---
Title: "Why GitHub and how to use it?"
Author:
  - name: Miguel P Xochicale
    affiliation: University of Birmingham
Address:
  - code:    1
    address: Department of Electronic, Electric and System Engineering, University of Birmingham, UK
Contact:
  - perez dot xochicale at gmail dot com
Editor:
  - Name Surname
Reviewer:
  - Name Surname
  - Name Surname
Publication:
  received:  Dec,  31, 2017
  accepted:  Sep, 1, 2018
  published: Sep, 1, 2018
  volume:    "**1**"
  issue:     "**1**"
  date:      December 2017
  number: 1
Repository:
  article:   "https://github.com/mxochicale/blogpost-submission-whygithub/tree/master/article"
  code:      
  data:      
  notebook:  
Reproduction:
  - "Original article (title, authors, journal, doi)"
Bibliography:
  bibliography.bib

---

# Introduction

These are some of the basics of version control [GIT](https://git-scm.com/),
a system to keep track of code, and the use of ([GitHub](https://github.com/))'s
syntax which providing such services.

Generally speaking, "GitHub has become the world’s leading repository of 
open-source computer code" [5] and hosts many open source projects for machine 
learning and deep learning such as [tensorflow](https://github.com/tensorflow)
, [keras](https://github.com/keras-team/keras), [theano](https://github.com/Theano/Theano)
, among others. But that is not the only attractive part of GitHub,
it can also be used for scientific writing where you can have open discussions 
for your work. Esentially, the openness of GitHub plays a crucial role in 
scientific research [4].

One interesting project is [ReScience](https://github.com/ReScience/),
which its goal is to make available the explicit replication of already published research.
ReScience lives on [GitHub](https://github.com/ReScience/) where each new implementation 
of computational studies are made available together with comments, explanations and tests [1].

The goal of the use of GitHub as a tool to share any of the proposals, posts, 
projects and anything related to Machine Learning for Mexico 
is to the increase of transparency and the improvement of reproducibility and 
its openness.

The following tutorial is based on the tutorial of O. Guest 2017 [2,3]


# Using GitHub

One main assumption is that the reader knows what a terminal is, as many of the
following lines are meant to be typed into the terminal. If you are not familiar
with the terminal, see this for a tutorial on how to use the
[command line](http://rik.smith-unna.com/command_line_bootcamp/).


## Installing git in Ubuntu
```
sudo apt-get update
sudo apt-get install git
```

## Create a New Repo
To create a new repository on GitHub go to: [https://github.com/new](https://github.com/new)

## Get Unlimited Private Repositories
Sign up for the academic/student pack on GitHub as many lab projects
(also known as [repositories](https://help.github.com/articles/github-glossary/#repository) or repos)
might need to be private (until publication, of course) and non-academics do
not get unlimited free private ones. [Sign up here](https://education.github.com/pack) —
they only need your academic (.ac.uk or .edu, etc.) email address to associate it with your account.

## Set up your git
Before to start using git in terminal, you have to setup your githubusername and
your email as follows
```
git config --global user.name "githubusername"
git config --global user.email "user@sth.sth"
```


## Clone a Repo
[Cloning](https://help.github.com/articles/cloning-a-repository/) means getting
a repository for the first time. So to download a whole repository for the first
time (e.g., my [blogpost-submission repo](https://github.com/ML4MX/blogpost-submission)):
```
git clone https://github.com/ML4MX/blogpost-submission
```
This command makes different new directories called, for instance: ```article```.
So you would need to change directory in order to see your newly downloaded files,
i.e., ```cd```, like so:
```
cd article
```
Then you can ```ls``` and ```ls -a``` to see all your files.
Feel free to actually ```clone``` blogpost-submission repository as you cannot
break it on GitHub since you do not have ```push``` rights.

## Add Files
[Adding](https://help.github.com/articles/adding-a-file-to-a-repository/) a file
means asking version control to start watching it, but it is not yet in the
history of your repository.
Just adding is not enough! All ```add``` does is say add this file to queue of
files to be ```commit```ted (the next section). You can be explicit and name
the files you want to add (all other files will not be added):
```
git add filename_1 filename_2... filename_n
```
Alternatively, you can add everything (except the things in your
  [```.gitignore```](https://help.github.com/articles/ignoring-files/) file):
```
git add -A
```
If you *just* ```add``` a file, it is not safe yet!
It *needs* to be ```commit```ted (next section) to be safely under version control!


## Commit Files
[Committing](https://help.github.com/articles/github-glossary/#commit) is adding
all the files to version control, although *not* to the server (the next section).


To commit everything you have just ```add```ed:
```
git commit -m "I've just made some very dramatic changes"
```
For your files to be 100% safe make you *must* also ```push``` them (the next section).
Only ```commit```ting makes files be under version control on your local machine,
e.g., your laptop, but they will *not* be accessible from another computer.


## Push Files
[Pushing](https://help.github.com/articles/pushing-to-a-remote/) ```commit```s,
and therefore files, makes your changes enter into the version control system on
the server as well as your local machine, so on GitHub.
So pushing is the superior form of backup and version control because it means
that there are at least two copies of your work *and* its history: one local copy
(the stuff you were just working on) and one server-side copy
(what you just ```push```ed).

Once everything you need is ```add```ed and ```commit```ted, it is time to ```push```.
Many ```add```s may be in one ```commit```, many ```commit```s may be in one ```push```.
But there is no reason to limit yourself to pushing once a day.
Push as often as possible pretty much, is my advice.

Unsurprisingly, as you might guess, to ```push``` you type:
```
git push origin master
```

## Check the Status
To check what is going on, what changes have been made, compare your local
repository's status with that of the server, etc., type:
```
git status
```
This command will often tell you what you need to do given the current changes
you have made, e.g., tell you you need to ```push``` your ```commit```s.
If you are unsure of anything, running ```git status``` should give you a hint
about what the next command you want to run is.

Importantly, if you have made server-side changes, i.e.,
you did some work on *machine A* and ```push```ed all that work to the server
and now you are on a completely different *machine B* and need to get back to
working on your repo, you need to tell the repo on this different machine B to
check the server for changes.
This can be done by asking your local git, on B, to
[fetch](https://help.github.com/articles/fetching-a-remote/) the changes from the server:
```
git fetch
```

Bear in mind that ```fetch``` *does not download any files*, it merely updates
what your local git knows about the changes you did on machine A which you then ```push```ed
to the server.
After ```fetch```ing, you may run ```git status``` as then the information on
the differences between your local files and those on the server will be correct.
Otherwise, if you just run ```git status``` you risk getting the wrong information
about what is on the server versus your local repo.

## Discard Changes
If you made some local changes and you do not want them around at all — you just
want what is on the server, you can run:
```
git stash
```
This discards all your local changes that have *not* been ```add```ed
or ```commit```ted.

## Pull Files
Pulling means getting stuff from the server. If you have made changes at work and
then go home and want to continue working where you left off, you run:
```
git pull
```
Unsurprisingly, ```pull``` does the opposite of what ```push``` does. It downloads
all the files you previously pushed to the server from work on your home computer.



# More tutorials

This is an  interactive tutorial that teach you everything of GitHub in about 
15 minutes at [try.github.io](https://try.github.io/levels/1/challenges/1)



# References
[ [1] Reproducible Science is good. Replicated Science is better. ](https://rescience.github.io/)  
[ [2] O. Guest, Git (and GitHub) Cheat Sheet in Github, Nov 2017](https://github.com/oliviaguest/neuroplausible/blob/master/_posts/2017-11-5-github.md)    
[ [3] O. Guest, Git (and GitHub) Cheat Sheet in blog, Nov 2017](http://neuroplausible.com/github)    
[ [4] P. Klemm, Use Github for Scientific Writing, July 2016](http://paulklemm.com/blog/2014-07-16-use-github-for-scientific-writing/)    
[ [5] M Banksm, We need github for academia research, April  2017](http://www.slate.com/articles/technology/future_tense/2017/04/we_need_a_github_for_academic_research.html)    
