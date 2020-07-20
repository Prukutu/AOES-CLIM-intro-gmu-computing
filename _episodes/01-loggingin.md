---
title: "How to login"
teaching: 5
exercises: 0
questions:
- "Why do I need to login to another computer?"
- "How do I login to COLA computers?"
objectives:
- "Explain why it is necessary to login to another computer"
- "Explain what computer systems exist at COLA to log into"
- "Explain how to login to the COLA computers from a learner's computer"
keypoints:
- "COLA computers that you can log into are cola1-7"
- "Secure shell (ssh) software is needed to login to COLA computers"
---
### Why do I need to login to COLA computers instead of using my own computer?
1. In atmosphere, ocean, and climate science most of data analysis work is done on Unix or Linux computers. These types of computers have more computational capability, more memore, and disk (or hard drive) space than a personal computer.  We need this to handle the many large datasets used in climate data analysis.  
2. COLA computers already contain the datasets we will work with.  These datasets are too large for your home computer and would take months to download. 
3. Unix computers use a command line interface that allow us to automate our data processing tasks much faster than a graphical user interface (GUI).  

### COLA Computers

The Center for Ocean-Land-Atmosphere Studies (COLA) in the Department of Atmospheric, Oceanic, and Earth Sciences (AOES) has Linux computers used to analysis of Climate Data.  They consist of cola1, cola2, cola3, ... , cola7.  These are the computers we will use in this class.  

### Setting up Software for your computer

To login to the COLA computers, you need secure shell (ssh) software. The software differs based on what type of computer you have. 

#### macOS
For a Mac computer, use software called [Xquartz](https://www.xquartz.org/)
#### Windows
For a Windows computer, use software called [MobusXterm](https://mobaxterm.mobatek.net/)

.challenge
## Download and install the correct ssh software for your computer. 
.{challenge}

## In this class, you can
* Raise your hand when you need assistance or have a question
* Indicate you are done with a Challenge in the colaborative document
.{callout}

### Logging in

You received a username and password from our system administrator.  You will need this to login to the COLA computers.

_macOS_
Launch the XQuartz software you downloaded and select `Shell`-> `New Window` from the menu in the upper left.
A window will appear that looks something like (look may vary depending on version of macOS and/or some default settings in `Xquartz`):

![Xquartz window](assets/img/Xquartz-open.png)

To connect to the computer `cola3` , type the following and replace `username` with your username:

~~~
$ ssh -Y -l username@cola3.gmu.edu
~~~
{: .language-bash}

_Windows_
Launch the MobusXterm software you downloaded.  Click `Session`->`SSH` 

## Login to a different cola computer
COLA computers are cola1, cola2, cola3, ... , cola7
Choose a computer other than cola3 and login to it.
.{challenge}
