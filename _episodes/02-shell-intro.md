---
title: "Shell Commands"
teaching: 5
exercises: 5
questions:
- "How do I use the Unix shell?"
objectives:
- "Introduce Unix Commands, switches, and how to get more info"
keypoints:
- "Most commands take options (flags) which begin with a `-`."
- "Identify the actual command, options, and filenames in a command-line call."
- "Highlight some switches that will be particularly useful."
keypoints:
- "Unix commands consist of the command, options or switches, and input to the command"
- "Additional switches can be found using `man`, `info` or `--help`"

---
### Background

Now that you have logged into the COLA computers, the computer is waiting for you to tell it what to do.

Humans and computers commonly interact in many different ways, such as through a keyboard and mouse, touch screen interfaces, or using speech recognition systems. The most widely used way to interact with personal computers is called a **graphical user interface** (GUI).
With a GUI, we give instructions by clicking a mouse and using menu-driven interactions.

While the visual aid of a GUI makes it intuitive to learn, this way of delivering instructions to a computer scales very poorly.
Imagine the following task:
for a literature search, you have to copy the third line of one thousand text files in one thousand different directories and paste it into a single file.
Using a GUI, you would not only be clicking at your desk for several hours, but you could potentially also commit an error in the process of completing this repetitive task. This is where we take advantage of the Unix shell.

The Unix **shell** is used to receive commands telling the computer what to do. (Note: in the course, the name "Unix" is used, but everything said about "Unix" also applies to "Linux", which is an open-source implementation with many different versions. The COLA computer systems actually run a version of Linux called CentOS.) The Unix shell is both a **command-line interface** (CLI) and a scripting language, allowing repetitive tasks to be done automatically and fast.
With the proper commands, the shell can repeat tasks with or without some modification as many times as we want.
Using the shell, the task in the literature example can be accomplished in seconds.

### The Shell

The shell is a program where users can type commands to interface with the computer.
With the shell, it's possible to invoke complicated programs like climate modeling software or simple commands that create an empty directory, often with only one line of code.
The most popular Unix/Linux shell is **bash** (the Bourne Again SHell --- so-called because it's derived from a shell written by Stephen Bourne).
Bash is the default shell on most modern implementations of Unix and in most packages that provide Unix-like tools for Windows.

When the shell is first opened, you are presented with a **prompt**,
indicating that the shell is waiting for input.

~~~
$
~~~
{: .language-bash}

The shell typically uses `$ ` as the prompt, but may use a different symbol.
In the examples for this lesson, we'll show the prompt as `$ `.
Most importantly:
when typing commands, either from these lessons or from other sources,
*do not type the prompt*, only the commands that follow it.

Many of you indicated in the Pre-Course Survey that you use the Unix shell daily or weekly. Often students know a small set of basic commands, but very few useful options or switches and are not familiar with commands that can greatly help your work and the work we will need to do in this course.  Therefore, we will review some Unix basics here and you will review some additional helpful commands on your own prior to next class (note that the possibilities of what you can do with shell commands is practically limitless - feel free to read up, search the Internet and explore to learn more).

`ls` means list the contents of the current directory.
~~~
$ ls
~~~
{: .language-bash}

~~~
$ ls -F /
~~~
{: .language-bash}


`ls` is the **command**, with an **option** `-F` (also called **switches** or **flags**) and an **argument** `/`.

Unix commands have many **options** that are very useful.  Let's look at some for `ls`

> ## Exploring More `ls` Flags
>
> You can also use two options at the same time. What does the command `ls` do when used
> with the `-l` option? What about if you use both the `-l` and the `-h` option?
>
> Some of its output is about properties that we do not cover in this lesson (such
> as file permissions and ownership), but the rest should be useful
> nevertheless.
>
> > ## Solution
> > The `-l` option makes `ls` use a **l**ong listing format, showing not only
> > the file/directory names but also additional information such as the file size
> > and the time of its last modification. If you use both the `-h` option and the `-l` option,
> > this makes the file size '**h**uman readable', i.e. displaying something like `5.3K`
> > instead of `5369`.
> {: .solution}
{: .challenge}

> ## Listing in Reverse Chronological Order
>
> By default `ls` lists the contents of a directory in alphabetical
> order by name. The command `ls -t` lists items by time of last
> change instead of alphabetically. The command `ls -r` lists the
> contents of a directory in reverse order.
> Which file is displayed last when you combine the `-t` and `-r` flags?
> Hint: You may need to use the `-l` flag to see the
> last changed dates.
>
> > ## Solution
> > The most recently changed file is listed last when using `-rt`. This
> > can be very useful for finding your most recent edits or checking to
> > see if a new output file was written.
> {: .solution}
{: .challenge}

### Getting help

`ls` has lots of other **options**. There are two common ways to find out how
to use a command and what options it accepts:

1. We can pass a `--help` option to the command, such as:
    ~~~
    $ ls --help
    ~~~
    {: .language-bash}

2. We can read its manual page with `man`, such as:
    ~~~
    $ man ls
    ~~~
    {: .language-bash}

3. Alternatively, Linux systems and many Unix systems have a differently-formatted manual invoked with `info`, such as:
    ~~~
    $ info ls
    ~~~
    {: .language-bash}

### More about options in Unix commands

You may have noticed that there may be single-dash options, e.g., `ls -F`
and double-dash options, e.g., `ls --help`.
You will usually see both kinds listed when you get help for a command. 

Single-dash options are always single characters, and they can be chained together, e.g.: `ls -asr` is the same as `ls -a -s -r`. 

Double-dash options are longer strings, usually in "plain English", and must be listed separately, 
e.g.: `ls --all --size --reverse`. 

Usually the order doesn't matter - but check the documentation if things do not behave the way you expect.

Some options have both forms, some have one or the other. Single-dash options are the original approach from the early days of Unix, but restricts the number of options that can be defined, so double-dash was developed to allow for limitless options.

Finally, some options take arguments, e.g.: `ls --color=always`, which prints the names of files and directories in different colors depending on their types. Again, see documentation for valid choices.
