---
title: "Shell Commands"
teaching: 0
exercises: 0
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
- "Additional switches can be found using `man` or `--help`"

---
### Background

Now that you have logged into the COLA computers, the computer is waiting for you to tell it what to do. In this class, we will also work on the NCAR supercomputer.  Both use the Unix shell to receive commands telling the computer what to do.  

### The Shell

The shell is a program where users can type commands.
With the shell, it's possible to invoke complicated programs like climate modeling software or simple commands that create an empty directory with only one line of code.
The most popular Unix shell is Bash (the Bourne Again SHell --- so-called because it's derived from a shell written by Stephen Bourne).
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

Most of you (80%) indicated in the Pre-Course Survey that you use the Unix shell daily or weekly. I have found in previous classes than many times students know a small set of basic commands, but very few useful options or switches and are not familiar with commands that can greatly help your work and the work we will need to do to run Earth System Models on a super computer.  Therefore, we will review some Unix basics here and you will review some additional helpful command on your own prior to next class.

`ls` means list the contents of the directory I am in
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

2. We can read its manual with `man`, such as:
    ~~~
    $ man ls
    ~~~
    {: .language-bash}

