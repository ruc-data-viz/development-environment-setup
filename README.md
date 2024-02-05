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
* **Jupyter**: notebook environment for developing in Python

The following tools are optional. VSCode is technically optional but is highly recommended. VSCode is so popular that you may find it harder to find help online and from your classmates if you choose another integrated development environment (IDE).
* **VSCode**: free IDE by Microsoft (optional)
* **Poetry**: tool for keeping track of Python dependencies (optional in this class)

It is helpful to practice installing these and other useful tools on your own so you can get comfortable searching the internet for the documentation on a new tool, reading the instructions, and learning how to use it on your own. This skill will help you in this course as you try new tools, and will help you professionally as you grow an ability to make independent contributions to software and data science teams.

In the first class, we tried installing these tools without any hints besides where to find them on the internet. With that exercise complete, this tutorial provides all the required commands to install these on your own, along with a short introduction to each.


## Git and GitHub

### Introduction

Git is a distributed version control system and exists to meet two needs that are ubiquitous in programming: (1) the need to track which *version* of a file we are working on (including any changes we may have made to it) and (2) the need to ensure that others we are working with can access that same version. If you have ever worked on a programming project (or even any other computer file, like an essay or assignment) and found yourself saving multiple copies titled `final.zip`, `final1.zip`, `final-final.zip`, `final-final-team-comments.zip`, etc. then Git can help. Git is especially important for programming on a team because as a distributed version control system, it not only tracks versions of our files, but also helps us store them in the cloud so anyone we are working with can access them.

### GitHub: collection of Git repositories

A collection of files version controlled in Git are called a *repository*. Repositories containing software also often contain other documentation files, including a `README.md` which explains the purpose of the repository and provides instructions to install it as a user or to contribute to it as a developer. This file (and the course syllabus along with other documentation we will use throughout the course) is a `README.md` file! Getting these files from the internet or a cloud environment to your local computer is called *cloning* the repository. Repositories are often called "repos" for short.

In this class, our repositories will be hosted on the internet via [GitHub](https://github.com/) which is an online tool for hosting Git repositories. The course repositories can be found [here](https://github.com/ruc-data-viz). This [tutorial](https://github.com/ruc-data-viz/development-environment-setup) is a Git repository. The [course syllabus](https://github.com/ruc-data-viz/2024-spring-syllabus) and other instructional materials which will be provided throughout the semester are also Git repositories.

### Installation

Git's [website](https://git-scm.com/download/) has straightforward instructions on installation. There are links for Mac, Windows, and Linux / Unix. Follow the link for the operating system you use and download the installer. Once downloaded, run the installer, using administrator privileges if necessary, and keep all default settings.

### Setting Up a GitHub Account

Click here to [join GitHub](https://github.com/join) and create an account online if you do not already have one. Having a GitHub account is required to complete assignments in this course.

### Helpful Videos

A helpful 15 minute video on Git is available [here](https://www.youtube.com/watch?v=USjZcfj8yxE). A helpful 20 minute video on GitHub is available [here](https://www.youtube.com/watch?v=nhNq2kIvi9s).

### Useful Commands

We interact with Git through a command line interface (CLI) in a shell or through an integrated development environment (IDE). Some of the most basic Git commands are provided here for reference. If you do not yet have a shell or an IDE set up, CLIs and IDEs will be introduced further on in this tutorial. If you are new to Git and development environment set up it may help to skip this section and return after completing the rest of the tutorial, including cloning your first repository and making your first repository.

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

For example, "Add a file" is a good commit message (grammatically speaking) since it would make sense to read the sentence "when applied, this change will add a file."

In practice (outside the context of this tutorial) commit messages should be both grammatically correct and descriptive. This is considered good manners and good professional practice so when your teammates inspect a log of commit messages to find the version of a file they need, that log will be easily read and understood. Do not use simple generic commit messages like "fixed" or "stuff". This is considered unprofessional and can make finding contributions by members of a team difficult.

#### Pushing Files

Once you have committed files, you can use `git push` to send the changes from your local computer to a remote repository. In our class, the remote repository will be hosted on GitHub. All assignments and quizzes will be submitted using `git push`!

```bash
git push
```

#### Seeing a List of Changes

Git logs all commits made. The log contains the message you or another author wrote when the commit was made, along with a unique *hash* (signature) of the files in the repository.

A hash is a number which will be different if any of the files in the repository have changed. The hash is designed such that the difference between two hashes will be extreme, even if the changes made to the files tracked were small. The hash is also designed such that there is an (extremely!) low probability any two different repository commits will have the same hash.

Hashes are often used to track differences between files or records in computer science, and are used to create one way (i.e., non-reversible) functions in computer security (e.g., for storing a password without revealing the password). Hashes are notably used in blockchain technology to track changes in financial records, in a manner similar to the way Git has used them for decades.

You can see all commits and their corresponding hashes with the following command. When viewing the log of commits, it is clear why it is important to have descriptive and grammatically correct commit messages so the log is legible.

```bash
git log
```

An obvious question to ask is what happens in the extremely unlikely event that two different versions of your repository have the same hash? There are more possible files than there are hashes so this is technically possible. Linus Torvalds, creator of Linux and Git, answered this question himself in an [archived post](http://web.archive.org/web/20120701221418/http://kerneltrap.org/mailarchive/git/2006/8/28/211065). The short answer is that Git will keep the older version (as if no changes have been made). In practice, this can only happen in the case of a maliciously designed cyber-attack, which would be expensive to execute (to search for file with the same hash) and ultimately have no impact (since Git keeps the older files)! Such issues are outside the scope of this course but fun history nonetheless.

#### Reverting to Previous Versions

To revert to a previous version, use `git checkout`. Replace `hash` with the unique signature of the commit you want to revert to. You can find the hash using `git log`.

```bash
git checkout hash
```

To checkout the `main` branch (i.e., the primary branch for the project) use the following command.

```bash
git checkout main
```

The ability to revert to an old version is useful when working on assignments, e.g., when you realize your previous work was closer to what you wanted to submit. To help provide plenty of opportunity to revert changes, be sure to commit often! Committing often is a critical best practice both academically and professionally. You should not spend multiple days on a software project without making any commits.

#### Seeing What Branch is Active

Use the following command to see a list of current branches available to change to. The branch you are currently on will have an asterisk next to it.

```bash
git branch
```

#### Making a New Branch

Use the following command to make a new branch. Replace `name` with the desired name of your new branch. There are conventions and best practices for using branches when developing on a professional team that are outside the scope of this tutorial and outside the scope of the course in general. In this class, use branches to try new ideas when working on assignments. If you have two ideas that you cannot implement simultaneously, make two separate branches for them and try them both out. Merge the one that works best into main.

```bash
git branch name
```

#### Merging a Branch into Current Branch

To merge a branch into another, first switch to the branch which is receiving the changes and then merge the branch from which the changes are merging. For example, use the following commands to merge `branch-b` into `branch-a`.

```bash
git checkout branch-a # Switch to branch a
git merge branch-b    # Merge branch b into branch a
```

## Terminal Environment

### What is a Command Line Shell?

In computing, a shell is a means through which users interact with the computer. While we often interact with modern computers through graphic user interfaces (GUIs), it is important in software and data science to be able to interact with computers through command line interfaces (CLIs) since many repetitive tasks can be easily automated through a CLI. This is done through a command line shell. Popular command line shells include Bash (Linux), Zsh (Mac), and PowerShell (Windows).

A shell is, at the most basic level, an infinite loop. It provides an opportunity for a the user to provide input, then provides a response or takes some action and repeats the loop by asking the user for more inputs. This happens until the user exits the shell, often using an exit command. In the case of a command line shell, all of this interaction happens through text. Note that the text used to interact with the shell must be exactly correct to bring about the intended result. Even a single missed character can change the meaning of a command!

The shells we will use in this class are based on Bash. You can learn about Bash in great detail from its [user manual](https://www.gnu.org/software/bash/manual/).

### Mac or Linux/Unix: Bash or Other Command Line Shells

#### Introduction

Command line shells are popular among many Linux / Unix users. Linux / Unix provide a standard *terminal* environment for interfacing through a shell. Mac, which is a descendent of Unix, provides a similar terminal environment. `Ctrl` + `Alt` + `T` opens a terminal in Ubuntu. Pressing `Command` + `Space`, typing "terminal", and pressing enter opens a terminal on Mac.

#### Installation

If you are using any variety of Unix, Linux, or MacOS you should not need to install any additional shells. Linux, for example, should come with Bash and MacOS, for example, should come with Zsh. You are welcome to try other shells if you like. Keep in mind that using a popular shell like Bash will make it easier to find support from the internet and your classmates. Some shells, like Bash and Zsh, have similar commands. Other shells, like PowerShell, have different commands. Changing shells can feel like changing dialects when speaking a language if they are similar shells, or even feel like learning a new language if switching to a very different shell!

### Windows: Git Bash

#### Introduction

Modern Windows provides CLIs through both Command Prompt and PowerShell. You can open Command Prompt by using `Windows` + `R` to open the run window, typing "cmd" and pressing enter. You can open PowerShell by opening the run window with `Windows` + `R` and typing "powershell". Both are useful for some tasks but many online tutorials for data science tools are written for users of Linux who would use Bash or a similar shell. To make sure you will be able to easily follow these tutorials, using Git Bash instead of Command Prompt and PowerShell is highly recommended! A common cause of errors in this class is attempting to use a command for Git Bash in Command Prompt or PowerShell.

#### Installation

Luckily, Git Bash should have installed when you installed Git! To use Git Bash, right click on a folder in Windows explorer and use the menu option to `Open Git Bash Here`. If you do not have a desktop shortcut for Git Bash already, you can find where it is installed by searching for Git Bash in the search bar, right clicking it in the results, and clicking "Go to file location". Then you can copy the Git Bash program from that location and paste it on your desktop as a shortcut.

### Useful Commands

Assuming you are using Bash, Zsh, or Git Bash, these commands should all work the same. Note that they might be different in other shells! Commands for any shell are easily searchable online if you get stuck or want to learn more. For example, if you are using Git Bash and forget how to change directories, just Google search "how to change directories in Bash". Yes, it is that easy! (And yes, you are allowed and encouraged to Google search for commands during any assignment, quiz, or exam in this class!)

#### Seeing Where You Are

It is important to know what folder you are in when working on the command line. Do this with the `pwd`, i.e., the "print working directory" command.

```bash
pwd
```

A common mistake, especially in Windows, is to open a shell in a folder you do not have permission to write data to or perform other operations in (e.g., your root folder or a protected system area). Be sure to check where you are in your shell. It is recommended to use the commands in this tutorial to create a folder for this course in an area like your desktop or another user folder.

#### Seeing Who You Are

It is important to know what user you are operating as on the command line. Find this out using the `whoami` command.

```bash
whoami
```

Usually, this will print your user name. This means you are operating as yourself! Sometimes, you might want to open your shell as an administrator or with other privileges. In this case, you can confirm you have done so by running the `whoami` command. It should then print `root`, `admin` or something similar. Do not run a shell as a root or administrative user unless you absolutely need to! Elevated privilege accounts will enable you to run commands that may harm system files your computer needs to run properly. The operating system assumes you know what you are doing if you are using an account with elevated privileges.

#### Moving Between Directories

The basic way to move around your file system in the terminal is using the `cd`, i.e., "change directories" command.

```bash
cd DIRECTORY
```

Here we replace `DIRECTORY` with the name of the folder or path we want to navigate to. For example, the following command will `cd` to the `my_folder` directory.

```bash
cd my_folder
```

The `cd` command provides useful shorthands for moving to common directories.

The tilde, `~`, is shorthand for your home directory and the following command will take you home.

```bash
cd ~
```

A shorthand that is useful when working on a shared system (e.g., a team server) is `cd ~USERNAME` where you can replace `USERNAME` with the name of the user who's home area you want to navigate to. You will use this command often if working on a server with teammates in a professional setting (and will likely have your teammates' user names memorized).

The dash, `-`, is shorthand for the last directory you were in. The following command takes you back to the last directory you were in.

```bash
cd -
```

Two dots, `..` is shorthand for moving up one directory.

```bash
cd ..       # Move up one directory
cd ../..    # Move up two directories
cd ../../.. # Move up three directories
```

#### Making Directories

Use the `mkdir` command to make new directories.

```bash
mkdir DIRECTORY
```

Here we replace `DIRECTORY` with the name of the folder we want to create. The following command will create a new directory called `my_folder`.

```bash
cd my_folder
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

The `ls` command provides many useful options.

```bash
ls -l     # Provides a long format list which shows dates and file permissions
ls -a     # Lists all files, including hidden files (hidden files begin with a dot)
ls -lat   # Combination of options listing all files in long format, newest first
ls -latr  # Combination of options listing all files in long format, oldest first
```

#### Finding Patterns in Files

The `grep` command can be used to find files in a directory. It is used like `grep pattern file`. The following example creates three files and then uses grep to search for a pattern between them.

```bash
echo "alpha" > file1.txt
echo "beta" > file2.txt
echo "gamma" > file3.txt
grep beta file*.txt  # Should output that pattern beta was found in file2.txt
```

Note that this example uses `>` to direct the output of the `echo` command into each file, and will create these files if they do not exist.

#### Redirecting Output and Chaining Commands

The CLI is most useful for automating tasks by chaining multiple commands together. Bash provides several ways to do this.

To simply run multiple commands on one line, separate them by a semi-colon. For example, do the following to move up one directory and then print the working directory.

```bash
cd ..; pwd
```

To execute the second command only if the first is successful, use `&&` to chain them together.

```bash
cd .. && pwd
```

To direct the output of one command into another Bash provides the ability to create *pipelines*.

The following command will list all files in the current directory, but will only show those with the pattern "2024" in their name. This command "pipes" the output of `ls` into `grep` to search through it.

```bash
touch file1_2023.txt
touch file2_2023.txt
touch file3_2023.txt
touch file1_2024.txt
ls | grep 2024
```

Note that this will only redirect standard output (known as STDOUT). Error messages (known as STDERR) will still be printed to the screen instead of being directed to the next command in the pipeline. To redirect both STDOUT and STDERR in a pipeline, use `|&` instead of `|`.

To redirect output to a file, use the `>` operator. This is what we did in the `grep` example above. As another example, the following command will output the list of files produced by `ls` to the file `my_file_list.txt`.

```bash
ls > my_file_list.txt # Overwrites my_file_list.txt with the output of ls
```

Note depending on how your system is configured, this will overwrite `my_file_list.txt`! To append the output to `my_file_list.txt` instead, use the `>>` operator.

```bash
ls >> my_file_list.txt # Appends the output of ls to my_file_list.txt
```

See the Bash manual pages on [pipelines](https://www.gnu.org/software/bash/manual/html_node/Pipelines.html) and [redirecting output](https://www.gnu.org/software/bash/manual/html_node/Redirections.html#Redirecting-Output) to learn more.

#### Shell Scripting

When using a shell to automate actions, commands are written in a *shell script*, i.e., a file with shell commands. The shell is then used to run the script which invokes the commands therein as if you were typing them in the shell. Shell scripting is outside the scope of this tutorial, but a basic example is shown here.

```bash
echo '#!/bin/bash' > hello.sh          # Make a file called hello.sh
echo 'echo "Hello World!"' >> hello.sh # Append a command to this file
cat hello.sh       # Inspect hello.sh to see what we wrote to it
chmod 755 hello.sh # Ensure we have permission to execute hello.sh
./hello.sh         # Runs the script to print Hello World!
```

Shell scripting is not part of this course, but it is useful to know in case you want to automate simple tasks. Normally, you would write a shell script in a file editor, but the above commands provide some examples of techniques learned here.

#### Comments

You may have noticed that we are providing helpful hints as to what our commands do after a `#` character. These are called comments. Comments are ignored by the shell and are useful for adding helpful documentation inside shell scripts. Remember that a good comment (outside the context of a tutorial) explains *why* a line of code is being written rather than explaining *what* the line of code does. Professionally, it is important to always write code which is understandable to you and your peers, ideally *without* needing to rely on comments to explain what you are doing. If you need to write a comment to explain what a line of code does, think of a simpler way to write that line so it is self-explanatory, and try using more descriptive variable and function names so your code reads like plain english.

#### Tip: Up Arrow!

Most shells will allow you to access the last commands you typed using the up arrow. This will prevent you from having to retype commands and can also be useful when you realize your last command generated an error. Simply use the up arrow to access that command, change what

#### Tip: Seeing Command History

You can see all the commands you have previously used by typing `history`.

```bash
history
```

This is particularly useful in a pipeline with `grep`.

```bash
history | grep "cd" # Finds all the commands previously executed with the pattern "cd"
```

#### Tip: --help and Other Standard Arguments

Many shell commands provide standard arguments. The two most ubiquitous are `--help` and `--version`. You can learn more about standards for shell commands in the [GNU Standards](https://www.gnu.org/prep/standards/html_node/Command_002dLine-Interfaces.html).

For example, you can get help with the `ls` command by typing the following.

```bash
ls --help
```

#### Tip: Google it!

As noted before, all of these commands are thoroughly documented online. You are always allowed to Google them and to Google errors you get in this course. Finding documentation online and using it to solve problems independently is a critical skill to learn academically and professionally. You can also use Large Language Models (LLMs) as provided by Bard, Bing Search, or use ChatGPT directly, as long as you adhere to the academic integrity policy and do not ask LLMs to do your work for you, and follow the Veterinary Dentists Law (see the [syllabus](https://github.com/ruc-data-viz/2024-spring-syllabus)) when using any artificial intelligence tools.

## Python

### Introduction

Python is a general purpose programming language ubiquitous in data science and machine learning. Python is known for its flexibility and insistence that there should be preferably only one way "right" to write a given program within the idioms of the language. Python programmers often call the best way to write a program using Python idioms the most *pythonic* way to write the program. Python is also known for enabling programs to be written in a manner that is easy and fun for those who are well versed in the language. An introduction to Python and programming in general is out of the scope of this tutorial but will be covered in detail later in this course.

### Installation

Python can be installed by following the online instructions [here](
https://www.python.org/downloads/).

To install Python click `Download` and run the installer.

### Installing Additional Python Packages

Python comes with a package manager called `pip` which is used to install new Python packages. The following commands install `numpy`, `pandas`, and `matplotlib`. These are three ubiquitous Python packages in data science which are used extensively in this course.

```bash
pip install numpy
pip install pandas
pip install matplotlib
```

### Advantages and Disadvantages of Python

Python is useful for quickly implementing programs and in many cases implementing production systems. Like any programming language it has advantages and disadvantages. An in depth discussion of programming language design is outside the scope of this tutorial, but at a high level, it is important to understand that Python is an *interpreted* programming language. This means that Python code for programs you write is run line-by-line in another computer program (the Python interpreter) which is downloaded for you when you download Python.

What that means practically is that another program sits between Python code and the actual way the computer executes the instructions provided in a Python program. Python has many incredible features which prevent these extra computations from slowing down program execution but it is not always as fast as a compiled language like C++, which is prepared for execution by a compiler that runs before the program executes. Importantly, a Python program might not always take the same amount of time to run, even if running on a fast computer with no other programs competing for the computer's resources. This makes Python a less ideal choice for running in real time. Many international standards forbid using Python (and many other programming languages) in safety critical systems.

Deep discussion of safety standards and the differences between interpreted and compiled languages is far outside the scope of this tutorial, but it is important to remember that interpreted languages like Python are often preferred for offline data analysis (e.g., playing back data from a self-driving car for analysis) while compiled languages are preferred for speed and control of execution (e.g., for running real time in the sensor processing system of a self-driving car). Safety critical systems often use standards compliant subsets of embedded languages, like C.

### Anaconda

[Anaconda](https://www.anaconda.com/) is a popular Python distribution that is ubiquitous in the data science community. You are welcome to use it in this class. Be aware that when using Anaconda you need to make sure you install packages to Anaconda's distribution of Python rather than installing them to another distribution of Python that may be on your system. If Anaconda is your preferred Python distribution then you also should make sure Anaconda appears first on your system `$PATH`. See the next section to learn about the `$PATH` and how to keep track of where different versions of Python are on your system.

#### Additional Considerations if Using Anaconda Professionally

Anaconda is a large (several GB) collection of Python tools and packages. The idea behind Anaconda is to make sure you have everything you need to use Python, which makes it especially popular in the data science community. Miniconda is a smaller collection (less than 1 GB). Keep in mind that if you are building a production system professionally, you should not have code you do not need on that system.

Having extra code on a system means extra maintenance, extra memory usage, and extra risk. To avoid this, you should import only the packages you directly need to make your product work, rather than using a distribution of Python that preemptively includes many packages you *might* need for convenience. In security-critical environments, you will be required to provide a software bill of materials (SBOM) that lists every software dependency in your system. You want to keep your SBOM as small as possible to make auditing your system for security as expedient as possible. Further, Anaconda is not free to use commercially. So there may be license fees to consider if using it professionally.

#### Conda vs. Anaconda

Anaconda is a distribution of Python that comes with many packages you may need. Conda is a package manager, which you can use to keep track of multiple versions of Python. You do not need to use both together. You can use Conda without Anaconda to keep track of multiple Python versions without also using Anaconda. Conda is free to use professionally. Managing multiple versions of Python is covered later in this tutorial.

## Understanding Your $PATH Variable and Other System Configuration Considerations

### Introduction

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

If you are running Unix / Linux / Mac, or using Git Bash, you can find tutorials online for changing your PATH in bash, by editing `.bash_profile` or other similar configuration files. A good explanation of this can be found [here](https://unix.stackexchange.com/questions/26047/how-to-correctly-add-a-path-to-path).

**Note**: be careful editing your PATH on the command line in Windows! Changing your PATH can change the way some programs will function. The best way to change your path is using a graphical tool provided by your OS or by editing files such as `.bash_profile`. Editing `.bash_profile` (covered later in this tutorial) is usually the preferred method since it is easy to change, but you should know how to use your OS' graphical tool as well since `.bash_profile` only applies when using `Git Bash` or `Bash` and there are times when you may wish to add something to your path and have it show up on your path all the time.

### Understanding Where Python is Installed on Your System

Like any computer program, Python lives in a folder on your system. Depending on your system, there are many different locations Python can be installed. Depending on what versions of Python you have installed, there may be multiple locations Python is installed on your system. To understand how you are interacting with Python, it is important to known where Python is installed. To find out where Python is installed you can do any of the following.

* Note where the Python installer said it is installing Python.
* On Windows, type Python in your search bar and click "Open file location" for the version you are interested in.
* On any OS, open your shell and type `which python`. Note that this will give you the path to a version of Python, but that might not be the version you want to find. You may need to explore the path output by `which python` as follows.

Note that you can find all areas where Python resides on your system (as long as they are in your `$PATH`!) with the following command.

```bash
which -a python python3
```

You can find other versions of Python by exploring these paths. Use `cd` to move to the area shown by the output of the command above and look for other versions of Python there. Note that some of these may be symlinks (i.e., shortcuts). We can use the following command to see where these symlinks point.

```bash
ls -al $(which -a python python3)
```

This runs the `which` command in a *sub-shell* and inserts its output in the current shell, effectively applying the `ls -al` command to each path returned by `which`. This will generate a long format listing of all the areas output by `which`, some of which may be shortcuts. On Windows, you may notice some of these shortcuts point to an installer. This installer will open a dialogue to install the latest Python. On Mac, you may notice that `python` or `python3` reference a common area on your system, something like `/usr/local/bin/python3`. Then this link points to the version of Python that runs when you type `python` or `python3`.

### Managing Multiple Versions of Python: Basics

One of the most common causes of confusion when setting up a Python development environment is having multiple versions of Python installed on your system. If you've installed a version of Python for a prior class, for personal use, or any other reason, and then installed another version of Python for this class, you will have multiple versions of Python on your system. This will not cause problems in this class (or at all) as long as you understand how to check which version of Python you are running at any given time and as long as you install required packages (i.e., anything you install with `pip` such as `matplotlib`) to the Python version you want to use for this course. There are many ways you will use and interact with Python in this class. We will cover how to be aware of and control the version you are interacting with in each of those cases here.

#### When Using Python on the Command Line

When using Python on the command line, you can see which version you are interacting with using the `--version` command.

```bash
python --version
```

To change the version of Python you interact with on the command line, you need to be sure that the version of Python you want to interact with appears first on your `$PATH`. Recall that you can see what is on your path using `echo $PATH | tr ':' '\n'`. Run this command first to see if the Python version you want is on your path.

If the Python version you want is behind another Python version in your `$PATH` or just not on your path at all, you will need to add its location to the beginning of your path. The easiest way to do this is by editing your `.bash_profile` file. The `.bash_profile` file is run by Bash or Git Bash every time you start the shell. It will run any commands you put there (like adding a folder to your path) for you.

You can see if you have a `.bash_profile` with the following command.

```bash
ls -al ~ | grep '\.bash_profile'
```

If this returns nothing, make one with the command `touch ~/.bash_profile` and open it in a text editor. Type the following inside that file then save and exit.

```bash
# Type this inside your .bash_profile file
PYTHON_PATH=/YOUR/DESIRED/PYTHON/PATH/HERE
export PATH="$PYTHON_PATH/Scripts:$PATH"
export PATH="$PYTHON_PATH:$PATH"
```

Be sure to write the path to where you found the version of Python you want to use. For example, for a username "john" on Windows, a `.bash_profile` might look as follows.

```bash
# Example .bash_profile
PYTHON_PATH=/c/Users/john/AppData/Local/Programs/Python/Python312
export PATH="$PYTHON_PATH/Scripts:$PATH"
export PATH="$PYTHON_PATH:$PATH"
```

This will run automatically every time you start your shell. If you want the changes to happen immediately, you can update your shell with this new profile using the `source` command.

```bash
source .bash_profile
```

You can check that your path was edited correctly by doing the following.

```bash
echo $PATH | tr ':' '\n' | head -n 5
```

This will show the first five folders in your PATH. You should verify the top two entries refer to your desired Python version. Now the `which python` and `python --version` commands should reference the desired versions.

**Note for MacOS:** When using Python on the command line in MacOS, the location where the `python` command points is usually a symlink to the actual location Python is installed. If your Python version is not what you expect it to be, you already tried editing your `$PATH` and you are using MacOS, this may be because the symlink is pointing to the wrong Python version. See [this](https://stackoverflow.com/questions/6819661/python-location-on-mac-osx) Stack Overflow answer to understand how to fix this.

#### When Using VSCode

When using VSCode (or any other IDE), it is important to understand that you might not be interacting with the same Python interpreter that you are interacting with in your shell! This may be true even if you have a shell open inside VSCode.

In VSCode, you can set your desired Python interpreter via the following steps.

1. Open the command palette via `Ctrl` + `Shift` + `P`
2. Type "Python: Select Interpreter"
3. Select your desired version of Python

#### When Using a Jupyter Notebook

When using a Jupyter notebook inside VSCode, you can see which version of Python the IDE is using to execute the notebook by looking in the top right corner of the notebook.

If you want to change the version VSCode uses for that notebook, click it, then click "select another kernel" in the command palette, then select your desired interpreter.

#### When Installing Packages with pip

When you install packages via pip, it is important to be sure you are installing them in a place where the version of Python you'll be using will find them. This means you must use the right installation of pip when executing `pip install PACKAGE` commands.

First, to see all the installations of pip on your system (that your $PATH can find) and where any shortcuts may be pointing to, use the following command.

```bash
ls -l $(which -a pip pip3)
```

To see which installation of pip you use when you type `pip` in your shell do the following.

```bash
which pip
```

You will notice that pip resides in a `Scripts` folder inside each installation of Python itself. You want to use the version of pip that resides in the `Scripts` folder for the version of Python you intend to install each module for. If you followed the instructions to edit your path and added the `Scripts` folder to your path then you should be using the right pip version for the Python version you are using. However, if you need to explicitly use another version of pip, you can type a specific command for the version of Python you want to install packages for. The following command shows how to install `mpmath` (a multi-precision arithmetic package) for different Python versions.

```bash
pip3.8 install mpmath  # Install mpmath for Python 3.8
pip3.11 install mpmath # Install mpmath for Python 3.11
pip3.12 install mpmath # Install mpmath for Python 3.12
```

### Managing Multiple Versions of Python: Helpful Tools

It is important to understand where Python is installed on your system, how to check which version you are interacting with at any given time, and how to interact with the version you intend to be interacting with. You can do this manually, or you can use one of many available tools. Managing your Python versions manually is recommended initially in an educational setting so you do not loose track of the functions the tools are performing for you. In a professional setting however, you will often need to keep track of many projects using many versions of Python, and using various tools to do this will be standard practice on a team.

* **pyenv**: pyenv is a tool for managing multiple versions of Python and easily switching between versions. Learn more on the [GitHub page](https://github.com/pyenv/pyenv).
* **venv**: venv is a tool for creating "virtual environments" which each have an independent set of Python packages installed on top of a base Python version. Learn more by reading the [documentation](https://docs.python.org/3/library/venv.html).
* **Poetry**: Poetry is a tool to manage what dependencies (versions of Python packages) each project you work on uses, while making those projects easy to build and publish so others can run them with the same dependencies and know they will work the same way. You can learn about Poetry on its [webpage](https://python-poetry.org/) and later on in this tutorial.
* **conda**: conda is a tool for creating and managing environments that contain different versions of Python that have different packages installed. You can learn more in its [documentation](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html).
* **Containers**: Containers (e.g., [Docker](https://www.docker.com/) containers) enable running software in its own process space and file system, so that software will function as if running on a dedicated computer. Containers function differently than virtual machines (e.g., Virtual Box) but use less resources from the host machine. Containers are popular and useful for packaging software in a way that facilitates integration with broader systems, and for helping to manage host machine resources in a shared environment. You are welcome to use them in this course. However, it is noted that containers are not a replacement for good dependency management in Python. Developing a container with poorly managed Python dependencies will yield just as unreliable of a system (with more complexity) as a pure Python package with poorly managed dependencies would have.

You are welcome to try out any of these tools in this course. All of them are optional, and you will be able to perform all assignments in this course without them. Remember when using these tools that you should still understand what tool you are interacting with Python through, in addition to knowing where that version of Python is installed, and how to confirm you are indeed interacting with the version of Python you think you are! This will help you avoid unexpected errors in both academic and professional settings.

## Contest

### Introduction

Contest stands for "console test" and is a tool written by Nick Sanchirico, who has taught this course in previous semesters, to facilitate grading of assignments in this course! This course is designed to provide a realistic experience, close to that of writing software on a professional team. To provide such an experience, all assignments are taken in GitLab, and graded on whether or not the tests pass. This is similar to the professional practice of software unit and regression testing (which will be covered later in this course) where an automated test suite runs each time a program is changed to ensure no functionality is broken.

Professionally, it is important to practice *Test Driven Development* (TDD) when writing software. Practicing TDD means not writing any code until you have first written a test that is failing! Then you may write code to make the test pass. This ensures you write only the code needed to make the test pass and provides a kind of checking mechanism. By thinking through the program twice (once to write the tests and once to write the program that makes them pass), we can use the agreement between our test cases and the actual output of the program as an indicator that we did not make a mistake. This is analogous to solving an algebra problem twice using two different methods to double check the solution.

### Installation

The instructions to install contest can be found [here](https://github.com/Lnk2past/contest).

As long as you have Python and pip set up, you should be able to install contest by opening Git Bash and typing the following command.

```bash
pip install contest
```

Using contest will be covered when we complete the first assignment for this course.

## Optional but Highly Recommended: VSCode

### Introduction

VSCode is a free integrated development environment (IDE) by Microsoft. An IDE is a collection of tools to develop software. Modern IDEs can be augmented with various packages and extensions. You are encouraged to search for useful extensions to help you as you take on assignments. While you are welcome to use any IDE you like for this class, VSCode is highly recommended. VSCode is so popular currently that getting help from your classmates and the internet will be much easier using it.

### Installation

VSCode can be installed from [here](https://code.visualstudio.com/download). Click the link for your OS and follow the instructions. You can use all default settings.

### Basics

A quick [7 minute introduction](https://www.youtube.com/watch?v=B-s71n0dHUk) to VSCode is recommended if you are completely new to it. A slightly longer [20 minute introduction](https://www.youtube.com/watch?v=ORrELERGIHs) is also helpful.

VSCode has many [keyboard shortcuts](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf). Learning them will help you work faster in it.

#### Opening VSCode

You should have a shortcut on your desktop to open VSCode. If not, create one by searching for VSCode in your OS, opening its location, copying, and pasting a shortcut to your desktop. You can also open VSCode by searching for it in your OS search bar as you would any other program.

To open VSCode in a particular folder, right click (or control-click for MacOS) that folder and click "Open with Code".

To open VSCode in a folder from your shell, type `code .`.

#### Buttons and Sections

The *activity bar* is on the left of VSCode's interface and has buttons for basic high level functions of VSCode.

These include the following.

* **Explorer**: explore files and navigate to where you need to develop code.
* **Search**: search the files in your project and perform find and replace tasks.
* **Source Control**: interact with Git through a UI instead of the command line.
* **Run and Debug**: run and debug the code you are writing.

#### Making New Files

Make a new file by clicking inside the explorer and typing `Ctrl` + `N`.

#### Opening a New Editor

Open an entirely new instance of VSCode with `Ctrl` + `Shift` + `N`.

#### Making and Running a Python Script

To make a Python script, create a new file with `Ctrl` + `N`. Type the following line and save the file as `hello.py`.

```python
print('Hello World!')
```

Click the play button in the top right to run your script.

A tutorial on getting started with VSCode in Python can be found [here](https://code.visualstudio.com/docs/python/python-quick-start).

#### Opening a Terminal

First, select your default terminal by pressing `F1` and then typing "Terminal: Select Default Profile". Select Git Bash or another preferred shell.

To open a terminal, press `Ctrl` + `Shift` + `` ` ``. This should now open the shell you selected as your preferred shell.

#### Running Commands

Above we pressed `F1` to open the command palette. The command palette can also be opened with `Ctrl` + `Shift` + `P`. Both of these are equivalent. Remember at least one! The command palette is used often.

#### Picking a Theme

It is fun to customize VSCode with themes. Press `F1` and then type "Preferences: Color Theme" or just "Theme". Use the up and down arrows to select a theme you like!

#### Helpful Extensions

VSCode is readily extensible and has an active community developing extensions for it. You are encouraged to try out new extensions during this class. Some that you will find helpful are listed here.

* **ms-python.debugpy**: Python debugger extension
* **ms-python.python**: Python extension
* **ms-python.vscode-pylance**: Python inline error checking and other support
* **ms-toolsai.jupyter**: Jupyter support
* **streetsidesoftware.code-spell-checker**: Spell checking inside your code

## Jupyter

### Introduction

Jupyter is a notebook environment for programming in Python. It allows you to see your data and visualizations of your data right next to your code. In this way, Jupyter enables practicing one of the most important principles from Tufte's The Visual Display of Quantitative Information, which states that visualizations should be embedded within the documents that describe them. For this and many other reasons, Jupyter is convenient for development, data visualization, and experimentation. We will go over Jupyter in detail and use it many times throughout this class.

### Installation

You can install Jupyter with pip as follows.

```bash
pip install notebook
```

Depending on your environment, you may also need to install the following additional packages.

```bash
pip install ipykernel
pip install ipython
```

JupyterLab provides even more functionality than Jupyter. We will not use it directly in this course but you are welcome to try it out for yourself!

```bash
pip install jupyterlab
```

### Basic Usage

Jupyter notebooks are comprised of *cells*. You can make a new cell and tell Jupyter whether you want this to be a code cell or a markdown cell. Use markdown cells to organize your notebooks by adding headers and documentation. Use code cells to add the code you want to run. You can add markdown and code cells with the `+ Markdown` and `+ Code` buttons respectively.

To run a Jupyter cell, press `Shift` + `Enter`. Note that unlike a Python script, where all lines will execute in the same order, it is easy to run Jupyter cells out of order. If done on purpose, this can be useful for prototyping and debugging (e.g., to run an interesting section of code multiple times before moving on to the next). However, if Jupyter cells are run out of order by accident, a program may not run as intended.

If you lose track of the order your Jupyter cells have been running in, you can use the `Restart` button to restart all cells. You can clear all old outputs with the `Clear All Outputs` button. You can run all cells in order (useful for checking the full functionality of a notebook before turning in an assignment or handing over to a colleague) using the `Run All` button.

One example of the usefulness of Jupyter cells is in training machine learning models. When training a machine learning model, you may wish to try to train it, look at some visualizations to see how well it fits the data, and then retrain it if it does not fit well before moving on to test it. You may implement this workflow in Jupyter by having a "train" cell, a "visualization" cell, and a "test" cell. Then you can run the train cell multiple times, checking the visualization cell after each (and potentially running that cell a few times to adjust your plots) before moving on to the test cell once you are satisfied.

## Optional: Poetry

### Introduction

When working on complex projects in Python, it can be difficult to keep track of what modules (e.g., `numpy`, `pandas`) and what versions of those modules your program depends on. Poetry is a useful tool for doing this. It is not mandatory in this course, but may be covered as a special topic depending on student interest.

### Installation

See the official installation instructions for Poetry [here](https://python-poetry.org/docs/#installing-with-the-official-installer).

For Windows users, the PowerShell method is recommended and summarized below.

Open PowerShell and run the following command.
```PowerShell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | py -
```

Use the following instructions to add Poetry to your path so Windows knows where to find it.

1. Search for System Properties.
2. In the System Properties dialog box, click the Advanced tab.
3. Click Environment Variables.
4. In the top list, scroll down to the PATH variable, select it, and click Edit. Note: If the PATH variable does not exist, click New and enter PATH for the Variable Name.
5. In the Variable Value box, scroll to the end of the variable. If there is no semi-colon (;) at the end of the current path, add one, and then enter the path to the MicroStation folder.
6. Click OK to close each dialog box.

You will need to find out where the installer placed Poetry's files. For Windows, these are usually at `%APPDATA%\pypoetry\venv\Scripts\`. This is the location you want to add to your path.

Confirm poetry works by closing and reopening Git Bash, and then typing the following command.

```bash
poetry --version
```

## First Task: Setting Up Git and Cloning a Repository with SSH

### Introduction

It is important to know how to clone a git repository from GitHub. There are several ways to do this, but in a professional setting this is often done securely via Secure Shell (SSH). This requires some setup which we will complete here and then move on to clone the course syllabus as a first task.

### How To Set Up Git

Providing your email helps Git track who changed what file. Git will eventually ask you for this information, but you can use the following commands to set it up ahead of time.

```bash
git config --global user.name "Your Name"
git config --global user.email "your@email.com"
```

### How to Set Up SSH Keys

To set up your SSH keys, first open Git Bash or the shell you are using for this class and then run the following command to generate a key.

```bash
ssh-keygen -t ed25519 -C ""
```

You can leave all fields blank, even the password, for this exercise. This will generate a public and a private key. You want to print (cat) the public key to your screen. In Git Bash or your preferred shell, do the following.

```bash
cat $HOME/.ssh/id_ed25519.pub
```

This will print the public key to your screen. Copy that key text.

Go to [https://github.com/settings/ssh/new](https://github.com/settings/ssh/new) and paste the public key. Give it a descriptive name.

### Clone the Syllabus

You are now ready to clone the course syllabus!

Go to a web browser and navigate to the syllabus page: [https://github.com/ruc-data-viz/2024-spring-syllabus](https://github.com/ruc-data-viz/2024-spring-syllabus).

Then click the green `Code` button, click SSH, and copy the text there. Run the following command in Git Bash or your preferred shell to clone the repository.

```bash
git clone PASTED-TEXT
```

Replace the PASTED-TEXT with the text you copied from the drop down under `Code` on GitHub. The actual command you run should look something like the following.

```bash
git clone git@github.com:ruc-data-viz/2024-spring-syllabus.git
```

Be sure to do this in an area you have permissions to write, such as your home area. You can get to your home area with the following command.

```bash
cd ~
```

Finally, you can open the syllabus in VSCode but navigating to the directory using the `cd` command and then opening VSCode using `code .`. The `.` tells VSCode to open in the current directory.

```bash
cd 2024-spring-syllabus
code .
```

Click on the `README.md` file to open it. There is a preview button in the top right corner of VSCode's screen which should allow you to view the file the same way it is viewed on the internet.

Now the our development environment is set up we are ready to begin coding. This would be a good time to practice many of the commands for Git and Bash / Git Bash that were covered earlier in this course.

Note that setting up your development environment can often be a frustrating part of joining any new professional software team. This is because the process can be different on different systems and different teams and individuals may prefer different tools. If the project is structured professionally though, team members should be able to contribute using their preferred environments. It only will get easier from here once we can start to use all the useful tools we just installed!

## Optional Task: How to Make Your Own Repository

### Introduction

It is useful know how to make your own Git repository and host it in GitHub. While the assignments in this course will exist as Git repositories that are already made for you, you might want to work on a tool, a personal project, or other assignments as Git repositories. Professionally, you can use GitHub projects as a way to showcase your skills to prospective employers.

### Making the Repository

Navigate to your public GitHub page in your web browser by typing `https://github.com/YOUR-USERNAME`. Click on `Repositories`.

If you've never made a repository before then this page should be empty. Click the `New` button.

Give the repository a basic but descriptive name, such as "example" or "hello-world". Give it a description such as "Example repository for educational use."

Make the repository Public. (You only get a set number of Private repositories when using the free version of GitHub so it is a good idea to use them sparingly.)

Add a .gitignore template. Choose the `Python` option in the dropdown. The .gitignore file tells Git which files *not* to track. It is important for professional repositories to always have an appropriate .gitignore to prevent Git from tracking unnecessary (or worse, private) files. Add a README.md file.

Leave the license set to `None` for now. Licenses are important when writing software personally or professionally but are outside the scope of this course.

Click `Create repository` to create your first repository!

### Cloning the Repository

As we did above, clone the repository you just created. Do this by navigating to the repository page. For example, if you named your repository "example" you can find it at `https://github.com/YOUR-USERNAME/example`. Click the green `Code` button to grab the repository name you need to clone it. You can use HTTPS or SSH.

Clone the file with the following commands.

```bash
git clone PASTED-TEXT
```

Replace the PASTED-TEXT with the text you copied from the drop down under `Code` on GitHub. The actual command you run should look something like the following.

```bash
git clone git@github.com:YOUR-USERNAME/example.git
```

### Adding Files to the Repository

Once you have cloned the repository, navigate into it with `cd`.

```bash
cd example
```

Use VSCode or the command line to create a file called `hello.py`. Populate the file with the following text.

```python
print("Hello World!")
```

Save the file. Take a moment to view the contents of the .gitignore file. Edit the README.md file if you wish.

### Pushing Back Up to GitHub

When ready, push your files back up to GitHub.

```bash
git status
git add .
git commit -m "Add hello.py"
git push
git status
```

Navigate back to your repository in your web browser to see your file there!
