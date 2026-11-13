Quick Start
===========

This will be covering how to run the code on your own machine,
and the organization of the project.

.. Note:: 
    This is written assuming the reader is somewhat familiar with a terminal and git,
    if you are not, it may be advisable to do so.

Prerequisites
#############

* A computer
* `Git <https://git-scm.com/>`_
* `The Python programming language <https://www.python.org/>`_ (an old version comes preinstalled on MacOS)

.. _quick-start-running-it:

Getting it running
#####################

Firstly, we'll be cloning the documenation onto our host machine, then changing
to it's directory. To do so, run:

.. code-block:: bash

    git clone TODO
    cd TODO

Next, we'll be installing the dependencies for this project. First, we'll be creating
something that'll store all our dependencies, called a venv (short for virtual environment).
After that, we'll be actually installing the requirements

.. code-block:: bash

    python3 -m venv ./venv
    source ./venv/bin/activate
    pip install -r requirements.txt

.. Note::
    On Windows, Python will be under just python, not python3

Now that we've installed everything, all that's left is to turn our .rst files into
code we can run in the web!

.. code-block:: bash

    sphinx-build -M html docs/source/ docs/build/

This will create the website's files in the docs/build folder. To open the hoem page,
open docs/build/html/index.html with your browser of choice. You can open this in a terminal,
or open up your file browser (Finder, File Explorer, or whatever else) and open it that way!

Congrats!! You've now ran the documentation on your computer! Now, if you want, you can start
editing it!

Editing the docs
#################

Unlike the above bits, this isn't meant to be read in any specific order, or be fully read at all.
Each section is stand-alone, so don't feel pressured to read all of it unless you need to!

.. Note::
    This assumes you have set up your working area similar to how we did in 
    :ref:`quick-start-running-it`. If you haven't, it shouldn't matter too much,
    but some wording may be confusing.

.. Note::
    This assumes you are familiar with reST, if not, `this <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_
    is a great resource I highly reccomend. Don't worry, you won't need to go through and memorize all of this or anything crazy,
    but if you're ever confused about something said here, it's a great place to look!

Project Structure
******************

This is a boring bit, but bear with us here. Inside the root directory consists a few things:

* docs (folder): This contains the source code for the website's pages, and is also where builds are
* venv (folder): If you created this, it stores all the stuff this project needs to run we didn't write ourselves
* .gitignore: This tells our version software (Git) what files to ignore
* .readthedocs.yaml: This tells readthedocs.com how to run our site

Going further into docs, we see two folders:

* build: The place where the code goes when sphinx turns the reST files into HTML and such
* source: The one we're most interested in, where all our source code is.

Finally, we see a bunch of things, glossing over the stuff we don't need to worry about,
we see a few folders, conf.py, index.rst, and a few other rst (reStructuredText) files.

The folders, if they start with an underscore, are the aforementioned things that don't matter to us.
If they don't, those all contain more rst files. The reason it's like that is purely for organization,
so if you needed to, per say, edit this file, you'd know where to look.

Next is conf.py. This tells sphinx (what we use to turn reST files into html files) how to run our project.
Unless you're trying to do some big changes (like change the theme of these docs), this won't matter to you as well.

Finally, ignoring all the other .rst files, we get to index.rst. This is the root file for our website, it's got
the home page, and links to every other file we ever use, directly or indirectly. Beyond that, it's not too special.

Deployment (for readthedocs.com)
***************************************

Whenever you update the git repository, readthedocs.com should see that and auto update. To send the changes you made on
your machine (local) to the git repository in the cloud (remote), simply run git push.

.. Note::
    You will need to have the login details for an account that has the ability to update the repository. If you do not,
    please contact a member of the EDC

If you need to edit the deployment info for readthedocs.com, the account that owns it is edc@synapseschool.org. You will,
however, need to get the password in person, as giving it out online would be, frankly, stupid. Sorry for the inconvienence!!