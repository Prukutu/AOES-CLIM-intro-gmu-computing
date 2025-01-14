---
title: "Logging into GMU (ORC) Computing"
teaching: 15
exercises: 5
questions:
- "Why do I need to login to another computer?"
- "How do I login to GMU computers?"
objectives:
- "Explain why it is necessary to login to another computer"
- "Explain what computer systems exist at GMU to log into"
- "Explain how to login to the GMU computers from a student's computer"
keypoints:
- "You need to use GMU computers for this class"
- "The GMU computer that you will log into is a cluster called HOPPER"
- "Secure (ssh) software is used to login to GMU computers"
---

### Why do I need to login to another computer instead of using my own computer?
In climate science most of our data analysis work is primarily done on either: 
1. Workstations (individual computers with multiple CPUs, large internal memory and access to large data storage)
2. Clusters (groups of dozens to ~100 connected workstations, often called "nodes"), or 
3. Supercomupters (very large clusters with hundreds or thousands of cores)
 
Such high-powered computers are almost always running a version of the Unix or Linux operating systems. These types of computers have more computational capability, more memory, and much more disk (or hard drive) space than a personal computer.  We need this to handle the very large datasets used in climate data analysis.  

Our research computers at GMU already contain many of the datasets we will work with. These datasets are too large for your home computer and would take weeks to months to download over the Internet. The Center for Ocean-Land-Atmosphere Studies (COLA) in the Department of Atmospheric, Oceanic, and Earth Sciences (AOES) has petabytes (i.e., thousands of terabytes, millions of gigabytes) of climate data from models and observations.

Linux/Unix computers use a command line interface that allow us to automate our data processing tasks much faster than a graphical user interface (GUI) that you may be familiar with in Windows or Mac OS.   

### GMU Computing - ORC and the clusters

The GMU Office of Research Computing maintains two separate clusters:

1. Hopper is a powerful cluster with over 10,000+ cores, including A100 80GB GPUs and DGX A100 40GB GPUsIt.
2. Argo is a 1500+ CPU core batch-processing cluster based on the condo model. 

We will use HOPPER in this class.  


### Setting up Software for your computer

There are several ways to connect to HOPPER. By far the easiest is via the [Dashboard in your browser](https://ondemand.orc.gmu.edu){:target="_blank" rel="noopener"}. This requires no special software installation or setup on your laptop. There are a number of commonly-requested apps provided from the dashboard, and a link to a more complete list of apps. 
1. Jupyter Lab - an interface to create and run Python notebooks on HOPPER
2. VS Code Server - A general integrated development environment that can run Jupyter Notebooks and provide advanced coding features

As with all things GMU, you will have to log in with your Mason ID and password. If you have your browser setup properly, you will only have to do this every 14 days (all secure GMU pages including the ORC Dashboard should recognize the same authentication). If you do not already have an ORC account, please see the [new user information](https://orc.gmu.edu/new-user-information/){:target="_blank" rel="noopener"}. The pre-course survey should have informed us whether you already have an account.



### Connecting to HOPPER via the Dashboard



### Connecting to HOPPER via `ssh`

As an alternative to the HOPPER desktop, you may access HOPPER via a terminal window on your laptop running secure shell (ssh) software. The software differs based on what type of computer you have. 

#### MacOS
For a Mac computer, use software called [Xquartz](https://www.xquartz.org/){:target="_blank" rel="noopener"}, which takes advantage of the fact that Mac OS is built on top of Unix.

#### Windows
For a Windows computer, use software called [MobaXterm](https://mobaxterm.mobatek.net/){:target="_blank" rel="noopener"}. Windows users can also install the Windows "Terminal" application from the Microsoft Store free of charge. The Terminal application can use `ssh` similar to Linux and MacOS. 

#### Linux
The default Shell for Linux operating systems is usually `bash`. On most versions of Linux, it is accessible by running the (Gnome) Terminal or (KDE) Konsole or `xterm`, which can be found via the applications menu or the search bar. If your machine is set up to use something other than `bash`, you can run it by opening a terminal session and typing `bash`.

> ## Download and install the correct ssh software for your computer
>
> If you have not already done so, it would be a good idea to download the correct `ssh` software for your computer 
>
> Follow the instructions on your computer to install the software
>
{: .challenge}


#### On macOS
Launch the XQuartz software you downloaded and select `Shell`-> `New Window` from the menu in the upper left.
A window will appear with a command line prompt, waiting for you to type. 

To connect to HOPPER, type the following and replace `username` with your Mason ID:

~~~
$ ssh -Y username@hopper.orc.gmu.edu
~~~
{: .language-bash}

Enter your password when prompted.

#### On Windows
With MobaXterm:
1. Launch the MobaXterm software you downloaded.  
2. Click `Session`->`SSH` 
3. In the `Remote host` box, enter `hopper.orc.gmu.edu` 
4. Check the `Specify username` box and enter your `username`
5. Click OK
6. Enter your password when prompted
7. Select No when asked to save your password.  

With the Windows Terminal application:
1. Launch the Terminal application from the Windows Start Menu. To connect to HOPPER, type the following and replace `username` with your Mason ID:

~~~
$ ssh -Y username@hopper.orc.gmu.edu
~~~
{: .language-bash}

If this is the first time you have logged in, you will be required to change your password.

> ## Password Policies
>
> * Keep your password secure and in a safe place - remember, this is your password for **everything** at GMU, not just this computer account!
> * Do not share your password.
> * No one should ever ask you for your password.  If you ever get an email or other electronic message asking for your password DO NOT respond to it, it is a phishing attempt.
> * Do not store your password on your laptop in plain text. 
> * Passwords must be changed every 6-months. You will get an alert from the university when the time is approaching.
> * Follow the Mason [Responsible Use of Technology Policies](https://universitypolicy.gmu.edu/policies/responsible-use-of-computing/){:target="_blank" rel="noopener"}
>
{: .callout}

