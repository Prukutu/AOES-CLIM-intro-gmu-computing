---
title: "Navigating Files and Directories"
teaching: 15
exercises: 5
questions:
- "How can I move around the file system on the computer?"
- "How can I see what files and directories I have?"
- "How can I specify the location of a file or directory on the computer?"
objectives:
- "Explain the similarities and differences between a file and a directory."
- "Translate an absolute path into a relative path and vice versa."
- "Construct absolute and relative paths that identify specific files and directories."
- "Use options and arguments to change the behaviour of a shell command."
- "Demonstrate the use of tab completion, and explain its advantages."
keypoints:
- "The file system is responsible for managing information on the disk."
- "Information is stored in files, which are stored in directories (folders)."
- "Directories can also store other directories, which forms a directory tree."
- "`cd path` changes the current working directory."
- "`ls path` prints a listing of a specific file or directory; `ls` on its own lists the current working directory."
- "`pwd` prints the user's current working directory."
- "`/` on its own is the root directory of the whole file system."
- "A relative path specifies a location starting from the current location."
- "An absolute path specifies a location from the root of the file system."
- "Directory names in a path are separated with `/` on Unix/Linux and Mac OS, but `\\` on Windows."
- "`..` means 'the directory above the current one'; `.` on its own means 'the current directory'."
---

The part of the operating system responsible for managing files and directories (where all your data are stored)
is called the **file system**.
It organizes our data into files,
which hold information,
and directories (also called 'folders'),
which hold files or other directories.
You are probably familiar with this idea from your own laptop. It works very similarly on HOPPER and other Linux/Unix systems.

Several commands are frequently used to create, inspect, rename, and delete files and directories.
To start exploring them, we'll go to our open shell window.

First let's find out where we are by running a command called `pwd`
(which stands for 'print working directory'). Directories are like *places* - at any time
while we are using the shell we are in exactly one place, called
our **current working directory**. Commands, by default, read, write and execute files in the
current working directory, i.e. 'here', so knowing where you are before running
a command is important. `pwd` shows you where you are:

~~~
$ pwd
~~~
{: .language-bash}

> ## Home Directory Variation
>
> The home directory path will look different on different operating systems.
> For ficticious student Nelle Nematode, on Linux it may look like `/home/nelle` 
> (or if she's at GMU: `/home/nnematod`),
> and on Windows it will be similar to `C:\Documents and Settings\nelle` or
> `C:\Users\nelle`
> (Note that it may look slightly different for different versions of Windows.)
> Meanwhile, on MacOS: `/Users/nelle`.
{: .callout}

To understand what a 'home directory' is,
let's have a look at how the file system as a whole is organized.  For the
sake of this example, we'll be
illustrating the filesystem on our scientist Nelle's computer.  After this
illustration, you'll be learning commands to explore your own filesystem,
which will be constructed in a similar way, but not be exactly identical.

On Nelle's computer, the filesystem looks like this:

![The file system is made up of a root directory that contains sub-directories
titled bin, data, users, and tmp](../fig/filesystem.svg)

At the top is the **root directory**
that holds everything else.
We refer to it using a slash character, `/`, on its own;
this is the leading slash in `/Users/nelle`.

Inside that directory are several other directories:
`bin` (which is where some built-in programs are stored),
`data` (for miscellaneous data files),
`Users` (where users' personal directories are located),
`tmp` (for temporary files that don't need to be stored long-term),
and so on.

We know that our current working directory `/Users/nelle` is stored inside `/Users`
because `/Users` is the first part of its name.
Similarly,
we know that `/Users` is stored inside the root directory `/`
because its name begins with `/`.

> ## Slashes
>
> Notice that there are two meanings for the `/` character.
> When it appears at the front of a file or directory name,
> it refers to the root directory. When it appears *inside* a path,
> it's just a separator.
{: .callout}

Underneath `/Users`,
we find one directory for each user with an account on Nelle's machine,
her colleagues *imhotep* and *larry*.

![Like other directories, home directories are sub-directories underneath 
"/Users" like "/Users/imhotep", "/Users/larry" or 
"/Users/nelle"](../fig/home-directories.svg)

The user *imhotep*'s files are stored in `/Users/imhotep`,
user *larry*'s in `/Users/larry`,
and Nelle's in `/Users/nelle`.  Because Nelle is the user in our
examples here we get `/Users/nelle` as our home directory.
Typically, when you open a new command prompt you will be in
your home directory to start.

### Moving around files and directories

~~~
$ cd 
~~~
{: .language-bash}

~~~
$ cd ..
~~~
{: .language-bash}

`..` is a special directory name meaning
"the directory containing this one",
or more succinctly,
the **parent** of the current directory.

The basic commands for navigating the filesystem on your computer:
`pwd`, `ls` and `cd`.  Let's explore some variations on those commands. 

What happens
if you type `cd` on its own, without giving
a directory?

~~~
$ cd
~~~
{: .language-bash}

How can you check what happened?  `pwd` gives us the answer!
It turns out that `cd` without an argument will return you to your home directory,
which is great if you've gotten lost in your own filesystem.

~~~
$ pwd
~~~
{: .language-bash}

~~~
/home/lortizur
~~~
{: .output}

Let's get some data and examples to work with for this lesson:

First, copy the file `/home/lortizur/classes/clim680_2022/data-shell.zip` to your home directory

~~~
$ cd
$ cp /home/lortizur/classes/clim680_2022/data-shell.zip .
~~~
{: .language-bash}

This is a lot to type,
but we can let the shell do most of the work through what is called **tab completion**.
If we type:

~~~
$ cp /home/lor
~~~
{: .language-bash}

and then presses <kbd>Tab</kbd> (the tab key on your keyboard),
the shell automatically completes the directory name:

~~~
$ cp /home/lortizur/
~~~
{: .language-bash}

Pressing <kbd>Tab</kbd> again does nothing,
because there are several possibilities;
pressing <kbd>Tab</kbd> twice brings up a list of all the options,
and so on.
This is called **tab completion**,
and we will see it in many other tools as we go on.

Once you have copied the file to your home directory, let's unzip it:

~~~
$ unzip data-shell.zip
~~~
{: .language-bash}


Let's go explore the directories we copied:

~~~
$ cd data-shell/data
~~~
{: .language-bash}

Check that we've moved to the right place by running `pwd` and `ls -F`

Here we used the **relative path** to specify the directory.  When you use a relative path with a command
like `ls` or `cd`, it tries to find that location from where we are,
rather than from the root of the file system.

However, it is possible to specify the **absolute path** to a directory by
including its entire path from the root directory, which is indicated by a
leading slash.  The leading `/` tells the computer to follow the path from
the root of the file system, so it always refers to exactly one directory,
no matter where we are when we run the command.

This allows us to move to our `data-shell` directory from anywhere on
the filesystem (including from inside `data`).  To find the absolute path
we're looking for, we can use `pwd` and then extract the piece we need
to move to `data-shell`.

~~~
$ pwd
~~~
{: .language-bash}

~~~
/home/lortizur/data-shell/data
~~~
{: .output}

~~~
$ cd /home/lortizur/data-shell
~~~
{: .language-bash}

Run `pwd` and `ls -F` to ensure that we're in the directory we expect.

> ## Two More Shortcuts
>
> The shell interprets the character `~` (tilde) at the start of a path to
> mean "the current user's home directory". For example, if Nelle's home
> directory is `/home/nelle`, then `~/data` is equivalent to
> `/home/nelle/data`. This only works if it is the first character in the
> path: `here/there/~/elsewhere` is *not* `here/there/home/nelle/elsewhere`.
>
> Another shortcut is the `-` (dash) character.  `cd` will translate `-` into
> *the previous directory I was in*, which is faster than having to remember,
> then type, the full path.  This is a *very* efficient way of moving back
> and forth between directories. The difference between `cd ..` and `cd -` is
> that the former brings you *up*, while the latter brings you *back*. You can
> think of it as the *Last Channel* button on a TV remote.
{: .callout}

> ## Absolute vs Relative Paths
>
> Starting from `/home/amanda/data`,
> which of the following commands could Amanda use to navigate to her home directory,
> which is `/home/amanda`?
>
> 1. `cd .`
> 2. `cd /`
> 3. `cd /home/amanda`
> 4. `cd ../..`
> 5. `cd ~`
> 6. `cd home`
> 7. `cd ~/data/..`
> 8. `cd`
> 9. `cd ..`
>
> > ## Solution
> > 1. No: `.` stands for the current directory.
> > 2. No: `/` stands for the root directory.
> > 3. Yes: Amanda's home directory is `/home/amanda`.
> > 4. No: this goes up two levels, i.e. ends in `/home`.
> > 5. Yes: `~` stands for the user's home directory, in this case `/home/amanda`.
> > 6. No: this would navigate into a directory `home` in the current directory if it exists.
> > 7. Yes: unnecessarily complicated, but correct.
> > 8. Yes: shortcut to go back to the user's home directory.
> > 9. Yes: goes up one level.
> {: .solution}
{: .challenge}
