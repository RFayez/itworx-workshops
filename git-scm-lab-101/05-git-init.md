A Git repository is a virtual storage of your project. It allows you to save versions of your code, which you can access when needed. To store a directory under version control you need to create a repository. With Git you initialise a repository in the top-level directory for a project.

To create a new repo, you'll use the `git init` command. `git init` is a one-time command you use during the initial setup of a new repo. Executing this command will create a new .git subdirectory in your current working directory. This will also create a new master branch.

When a directory is part of a repository it is called a Working Directory. A working directory contains the latest downloaded version from the repository together with any changes that have yet to be committed. As you're working on a project, all changes are made in this working directory.

## Task

### Populate a new project

We'll start off with creating a simple project. Go ahead and create a `README.md`{{open}} file. And add some content to the README.md

<pre class="file" data-filename="./README.md" data-target="replace">
# Simple HTML Project

This is my first simple HTML project tracked by git.
</pre>

Then another file called `index.html`{{open}} with simple HTML content.

<pre class="file" data-filename="./index.html" data-target="replace">
<&zwj;!DOCTYPE html>

<&zwj;html>
  <&zwj;head>
  	<&zwj;title>Page title<&zwj;/title>
  <&zwj;/head>

  <&zwj;body>
    <&zwj;h1>My First Heading<&zwj;/h1>
    <&zwj;p>My first paragraph.<&zwj;/p>
  <&zwj;/body>
<&zwj;/html>
</pre>

These two files will form the initial release of our small project.

Now that the project has been initialized with some files, let's inspect it from the command line. Switch to the Terminal section and use ```ls```{{execute}}, which will show you the two files which you have created.

So far we have established a basic project which we can track it's changes with `git`.

### Initializing a new repository / `git init`

As this is a new project, a new repository needs to be created. Use;

```git init```{{execute}}

to create an empty Git repository - basically a directory called `.git/` with subdirectories for **objects**, **refs/heads**, **refs/tags**, and template files. An initial HEAD file that references the HEAD of the master branch is also created. You will now have a .git directory, and you can inspect that with

```ls -a```{{execute}}

Inspect the contents of the `.git/` directory with:

```ls .git/```{{execute}}

which reveals all the files and directories that construct the repository. For your new empty project, it should show you three entries, among other things:

* a text file called **HEAD**, that has the content `ref: refs/heads/master` in it. This is similar to a symbolic link (a shortcut) and points at refs/heads/master relative to the HEAD file.
* a subdirectory called **objects/**, which will contain all the objects of your project. You should never have any real reason to look at the objects directly, but you might want to know that these objects are what contains all the real data in your repository.
* a subdirectory called **refs**, which contains references to objects.

### Inspect the repository / `git status`

You can view which files have changed between your working directory and what's been previously committed to the repository using the command:

```git status```{{execute}}

The output of this command is called the "working tree status". `git status` displays paths that have differences between the index file and the current HEAD commit, paths that have differences between the working tree and the index file, and paths in the working tree that are not tracked by Git (and are not ignored by **.gitignore**). The first are what you _would_ commit by running `git commit`; the second and third are what you _could_ commit by running `git add` before running `git commit`.

## ProTip

* Running `git init` in an existing repository is safe. It will not overwrite things that are already there.
* All files are "untracked" by Git until it's been told otherwise. The details of how is covered in the next step.