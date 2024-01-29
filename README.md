# Development Environment Setup Tutorial

This tutorial shows how to install the tools that will be used during this course. When programming professionally on a team, this is often called "setting up your development environment". Getting a development environment set up is often the first task any software or data science professional will take on when joining a new team.

As is typical on a professional team, we will not mandate exactly what tools must be used to perform the exercises in this course. For each assignment and quiz, as long as the tests pass, you will get full credit regardless of the tools you choose to use. You may attempt each any number of times and are encouraged to try out different tools as you do. The tools covered in this guide are only suggestions. You may find additional tools useful throughout the course and are welcome to use them. Some additional tools will be covered as we review special topics throughout the year.


## Tools for this Course

The following tools are required for this course. We will introduce all of them here and show how to install them.
* **Git**: distributed version control system
* **GitHub**: popular website for hosting Git repositories
* **Git Bash**: Linux-like command prompt for windows (comes with Git on Windows)
* **Python**: programming language ubiquitous in data science and machine learning (the latest version is 3.12 but any modern version > 3.8 will work for this class)
* **contest**: tool used in this course for grading assignments

The following tools are optional. VSCode is technically optional but is highly recommended. VSCode is so popular that you may find it harder to find help online and from your classmates if you choose another integrated development environment (IDE).
* **VSCode**: free IDE by Microsoft (optional)
* **Poetry**: tool for keeping track of Python dependencies (optional in this class)

It is helpful to practice installing these and other useful tools on your own so you can get comfortable searching the internet for the documentation on a new tool, reading the instructions, and learning how to use it on your own. This skill will help you in this course as you try new tools, and will help you professionally as you grow an ability to make independent contributions to software and data science teams.

In the first class, we tried installing these tools without any hints besides where to find them on the internet. With that exercise complete, this tutorial provides all the required commands to install these on your own, along with a short introduction to each.


## Git and GitHub

### Introduction

Git is a distributed version control system and exists to meet two needs that are ubiquitous in programming: (1) the need to track which *version* and of a file we are working on (including any changes we may have made to it) and (2) the need to ensure that others we are working with can access that same version. If you have ever worked on a programming project (or even any other computer file, like an essay or assignment) and found yourself saving multiple copies titled `final.zip`, `final1.zip`, `final-final.zip`, `final-final-team-comments.zip`, etc. then Git can help. Git is especially important for programming on a team because as a distributed version control system, it not only tracks versions of our files, but stores them in the cloud so anyone we are working with can access them.

### GitHub: collection of Git repositories

A collection of files version controlled in Git are called a *repository*. When a repository contains software, it often also contains other documentation files, including a `README.md` which explains the purpose of the repository and provides instructions to install it as a user or contribute to it as a developer. This file (and the course syllabus along with other documentation) is a `README.md` file! Getting these files from the internet or a cloud environment to your local computer is called *cloning* the repository. Repositories are often called "repos" for short.

In this class, our repositories will be hosted on the internet via [GitHub](https://github.com/) which is an online tool for hosting Git repositories. The course repositories can be found [here](https://github.com/ruc-data-viz). This [tutorial](https://github.com/ruc-data-viz/development-environment-setup) is a Git repository. The [course syllabus](https://github.com/ruc-data-viz/2024-spring-syllabus) and other instructional materials which will be provided throughout the semester are also Git repositories.

### Installation

Git's [website](https://git-scm.com/download/) has straightforward instructions on installation. There are links for Mac, Windows, and Linux / Unix. Follow the link for the operating system you use and download the installer. Once downloaded, run the installer, using administrator privileges if necessary, and keep all default settings.

### Setting Up a GitHub Account

Click here to [join GitHub](https://github.com/join) and create an account online if you do not already have one. Having a GitHub account is required to complete assignments in this course.

### Helpful Videos

A helpful 15 minute video on Git is available [here](https://www.youtube.com/watch?v=USjZcfj8yxE). A helpful 20 minute video on GitHub is available [here](https://www.youtube.com/watch?v=nhNq2kIvi9s).

### Useful Commands

We interact with Git through a command line interface (CLI) in a shell or through an integrated development environment (IDE). Some of the most basic Git commands are provided here for reference. If you do not yet have a shell or an IDE set up, CLIs and IDEs will be introduced further on in this tutorial.

#### Cloning

Using Git to download a version controlled repository from the internet (in this class) or a cloud environment (in many professional settings) is called *cloning* the repository.

The following command shows how to clone the syllabus.

```bash
git clone git@github.com:ruc-data-viz/2024-spring-syllabus.git
```

If you go to a Git repository on GitHub and click the green `code` button you will see the command you need to clone that repository. There are multiple commands you can use. We will cover those later in this tutorial.

#### Status

When you are inside a Git repository you can check the status of the repository (e.g., check if any files have changed) using the following command. Be sure to remember this command since it is used often!

```bash
git status
```

#### Adding Files

After we edit files in a repository, we must *add* them so git knows these are the files we want to commit and push from our local computer to the distributed repository where others will be able to clone them. Adding files is the first step to committing them, and is analogous to putting them in a box before we ship them (commit them).

The following command will add all files we have changed in the current repository.

```bash
git add .
```

The following command will add just `file.txt`.

```bash
git add file.txt
```

#### Committing Files

Once files are added, we can commit them into version control using `git commit`. The following command shows the most common way to do this and specifies a message with the `-m` flag.

```bash
git commit -m "Add a file"
```

Adding a message will help us track our changes later. A good commit message should always read as "When applied, this change will...{your message here}".

For example, "Add a file" is a good commit message since it would make sense to read the sentence "when applied, this change will add a file."

#### Pushing Files

Once you have committed files, you can use `git push` to send the changes from your local computer to a remote repository. In our class, the remote repository will be hosted on GitHub. All assignments and quizzes will be submitted using `git push`!

```bash
git push
```

#### Seeing a List of Changes

Git logs all commits made. The log contains the message you or another author wrote when the commit was, along with a unique *hash* (signature) of the files in the repository.

A hash is a number which will be different if any of the files in the repository have changed. The hash is designed such that the difference will be extreme, even if the changes were small. The hash is also designed such that there is an (extremely!) low probability any two different repositories will have the same hash. Hashes are often used to track differences between files or records in computer science, and are used to create one way (i.e., non-reversible) functions in computer security (e.g., for storing a password without revealing the password). Hashes are notably used in blockchain technology to track changes in financial records, in a manner similar to the way Git has used them for decades.

You can see all commits and their corresponding hashes with the following command.

```bash
git log
```

#### Reverting to Previous Versions

To revert to a previous version, use `git checkout`. Replace `hash` with the unique signature of the commit you want to revert to. You can find the hash using `git log`.

```bash
git checkout hash
```

To checkout the `main` branch (i.e., the primary branch for the project) use the following command.

```bash
git checkout main
```

The ability to revert to an old version is useful when working on assignments, e.g., when you realize your previous work was closer to what you wanted to submit. To help provide plenty of opportunity to role back changes, be sure to commit often! Committing often is a critical best practice both academically and professionally.

#### Seeing What Branch is Active

Use the following command to see a list of current branches available to change to. The branch you are currently on will have an asterisk next to it.

```bash
git branch
```

#### Making a New Branch

Use the following command to make a new branch. Replace `name` with the desired name of your new branch. There are conventions and best practices for using branches when developing on a professional team that are outside the scope of this course. In this class, use branches to try new ideas when working on assignments. If you have two ideas that you cannot implement simultaneously, make two separate branches for them and try them both out. Merge the one that works best into main.

```bash
git branch name
```

#### Merging a Branch into Current Branch

To merge a branch into another, first switch to the branch which is receiving the changes and then merge the branch from which the changes are merging. For example, use the following commands to merge `branch-b` into `branch-a`.

```bash
git checkout branch-a # Switch to branch a
git merge branch-b # Merge branch b into branch a
```

## Terminal Environment

### What is a Command Line Shell?

In computing, a shell is a means through which users interact with the computer. While we often interact with modern computers through graphic user interfaces (GUIs), it is important in software and data science to be able to interact with computers through command line interfaces (CLIs) since many repetitive tasks can be easily automated through a CLI. This is done through a command line shell. Popular command line shells include bash (Linux), zsh (Mac), and PowerShell (Windows). A shell is at its core an infinite loop. It provides an opportunity for a the user to provide input, then provides a response or takes some action and repeats the loop, asking the user for more inputs. This happens until the user exits the shell, often using an exit command. In the case of a command line shell, all of this interaction happens through text. Note that the text used to interact with the shell must be exactly correct to bring about the intended result. Even a single missed character can change the meaning of a command!

### Mac or Linux/Unix: Bash or Other Command Line Shells

#### Introduction

Command line shells are popular among many Linux / Unix users. Linux / Unix provide a standard *terminal* environment for interfacing through a shell. Mac, which is a descendent of Unix provides a similar terminal environment. `Ctrl` + `Alt` + `T` opens a terminal in Ubuntu. Pressing `Command` + `Space`, typing "terminal", and pressing enter opens a terminal on Mac.

#### Installation

If you are using any variety of Unix, Linux, or MacOS you should not need to install any additional shells. Linux, for example, should come with bash and MacOS, for example, should come with zsh. You are welcome to try other shells if you like. Keep in mind that using a popular shell like bash will make it easier to find support from the internet and your classmates.

### Windows: Git Bash

#### Introduction

Modern Windows provides CLIs through both Command Prompt and PowerShell. You can open Command Prompt by using `Windows` + `R` to open the run window, typing "cmd" and pressing enter. You can open powershell by opening the run window with `Windows` + `R` and typing "powershell". Both are useful for some tasks but many online tutorials for Data Science tools are written for users of Linux who would use bash or a similar shell. To make sure you will be able to easily follow these tutorials, using Git Bash instead of Command Prompt and PowerShell is highly recommended! A common cause of errors in this class is attempting to use a command for Git Bash in Command Prompt or PowerShell.

#### Installation

Luckily, Git Bash should have installed when you installed Git! To use Git Bash, right click on a folder in Windows explorer and use the menu option to `Open Git Bash Here`.

### Useful Commands

Assuming you are using bash, zsh, or Git Bash, these commands should all work the same. Note that they might be different in other shells! Commands for any shell are easily searchable online if you get stuck or want to learn more.

#### Seeing Where You Are

It is important to know what folder you are in when working on the command line. Do this with the `pwd`, i.e., the "print working directory" command.

```bash
pwd
```

#### Seeing Who You Are

It is important to know what user you are operating as on the command line. Find this out using the `whoami` command.

```bash
whoami
```

#### Moving Between Directories

The basic way to move around your file system in the terminal is using the `cd`, i.e., "change directories" command.

```bash
cd
```

#### Making Directories

Use the `mkdir` command to make new directories.

```bash
mkdir
```

#### Making Files

You can quickly make new files using the `touch` command. The following command will create a Python script file `script.py` if it does not already exist.

```bash
touch script.py
```

If the file already exists, its last modified timestamp will be updated to the moment the touch command was invoked but the file contents will not be changed.

#### Printing File Contents to the Screen

The `cat` command is used to print the contents of a file to the screen. In this command, `cat` is short for `concatenate` since we are concatenating the contents of the file to the buffer which is displayed on the screen.

The following commands create a file, add some text to it, and display this text to the screen.

```bash
echo "hello world" > file.txt
cat file.txt # Should print hello world
```

#### Listing Files in a Directory

Files in a directory can be listed using the `ls` command. This is important and will be used often.

```bash
ls
```

#### Finding Patterns in Files

The `grep` command can be used to find files in a directory. It is used like `grep pattern file`. The following example creates three files and then uses grep to search for a pattern between them.

```bash
echo "alpha" > file1.txt
echo "beta" > file2.txt
echo "gamma" > file3.txt
grep beta file*.txt  # Should output that pattern beta was found in file2.txt
```

## Python

### Introduction

### Installation

### Installing Additional Python Packages

Python comes with a package manager called `pip` which is used to install new Python packages. The following commands install `numpy`, `pandas`, and `matplotlib`. These are three ubiquitous Python packages in data science which are used extensively in this course.

```bash
pip install numpy
pip install pandas
pip install matplotlib
```

### Advantages and Disadvantages of Python
Important to understand professionally


### Understanding Your $PATH Variable

Your operating system will look for programs in the folders specified in your $PATH variable in the order they appear. If you are typing `python --version` on the command line and not seeing the version you just installed (e.g., you just installed Python 3.12 but `python --version` returns 3.8.3) then it is likely that your operating system is looking for Python in a folder that may contain an older version of Python before it looks in the folder that contains the newer version.

You can view what directories are in your `$PATH` using the following command.

```bash
echo $PATH | tr ':' '\n'
```

The first part of this command (`echo $PATH`) prints your `$PATH` to the screen. The second part of the command (`| tr ':' '\n'`) exchanges all the `:` characters for newlines so you can see the paths more clearly.

If this command confirms that your OS is looking for Python in the wrong place, then you need to edit your `$PATH` variable. It is possible to edit your `$PATH` on the command line but it is safer to do so using the OS' built in tools. To edit the $PATH on Windows do the following steps.

1. Search “Advanced system settings”
2. Go to “Advanced”
3. Click “Environment Variables…”
4. Click “Path” and click “Edit…”
5. Click “New”
6. Enter the path to the folder you want on your PATH.

### Helpful Videos


## Contest

### Introduction

### Installation


## Optional but Highly Recommended: VSCode

### Introduction

### Installation


## Optional: Poetry

### Introduction

### Installation


## First Task: Setting Up Git and Cloning a Repository with SSH

### Introduction

Important professionally

### How To Set Up Git

Providing your email helps Git track who changed what file.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### How to Set Up SSH Keys


