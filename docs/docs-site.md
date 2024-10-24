---
title: Creation of a docs site
tags:
 - documentation
 - docs
 - python-libraries
---

# Building a Docs Site

Let's be real without information the world doesn't move anywhere.  And the faster you find and
are able to deal with that information (and remember) the better things will be for you.  At least
that's what I am telling myself!

Anyways, the docs site (not just code documentation) has become a great place to store the things that
you **MIGHT** want to look up later.  Hey no one knows the future right.  So rather than relying on
your brain to **remember** it all, just have a single place to put that information so you can refresh
your memory, or have AI look it up using your own GPT on your archive of information (AWESOME!).

## The Docs Site

This method has a couple of things that are required in order to do thw work, oh and by the way,
we will be using python for this example.  We are going to be using poetry as our package manager 
and python3.10 but more recent should work just fine.  In addition, I will be working on a linux based platform but
windows should be just fine.  Our "docs" source is going to be mkdocs and by
the end of this we will have a working GitHub site that has our docs available to be searched and have
tagged environment that we can work from.

1. First things first, we need to have poetry installed in a virtual environment.  (Note if you have no idea what 
   poetry is you can read about it [here](https://python-poetry.org/)  My favorite way to install poetry is
   to use the installer.  From you shell execute the following (Make sure you aren't in any virtual env at this point
   one will be created for the poetry install itself)

    ```
    curl -sSL https://install.python-poetry.org | python3 -
    ```
   
1. Next we need to have a place for our project files.  For me, I usually have repositories located in my home directory
   ```~/repos```  that way I can just cd whenever I open my shell. Once your shell is where your projects are located
   we create a new project with poetry.  There will be a bunch of questions and answers you can use to build the project
   "your" way, but I would just use the bare bones as we will update it soon.

    ```
    poetry init blue-book
    ...
    ```
   
1. In your shell, cd in to the blue-book (or your project directory).  This is your project folder that you will 
   eventually upload to GitHub (oh you need a GitHub account and a repository as well).  We need to install a few 
   dependencies.  For each of the dependencies you will use the following command:

    ```
    poetry add mkdocs
    ```
   
    Note mkdocs is the primary project for our system.

    - proselint
    - gitdb2 
    - mkdocs-git-revision-date-localized-plugin
    - mkdocs-minify-plugin
    - mkdocs-section-index
    - mkdocs-newsletter
    - mkdocs-autolinks-plugin
    - mkdocs-exclude-search

     Note I will do a deeper dive on each of these dependencies as I figure out how to configure them in my own words.

1. Now that we have all of the dependencies set up we need to start our docs site.  To do this we use the following 
   command which will create all the files that mkdocs needs to create it for you.
 
    **NOTE** the '.' that is not there by mistake we want the docs site to be created in the root of the project.

    ```
    poetry run mkdocs new .
    ```
   
1. Now we can simply run the following to have a default setup page that we can modify and make our own.  The 
   program will tell you where you can direct your browser to see the default mkdocs and how to continue on.

    ```
    poetry run mkdocs serve
    ``` 
   
## Next Steps

Ok so this has gotten us up and going, but we have so much left to document.  But for now that's all I am going to 
write.  Hopefully this helps someone.





