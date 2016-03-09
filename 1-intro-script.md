[Start here](@@@)
@@ link to my first notebook

http://blog.jupyter.org/2015/07/07/project-jupyter-computational-narratives-as-the-engine-of-collaborative-data-science/

## Basics

This is the console.  This is where you start and stop notebooks, along
with other things.

[//]: # (@@running vs ...)

We'll start with a Python notebook.  You can pick the version of Python
to run; for demonstration purposes, let's use Python 3.  New... Python 3.

This opens a new window. You can go back to your Home window and open
up multiple notebooks in Jupyter.

New notebooks start as Untitled; click to change the name.

The main feature of a notebook is the code cell, here.  You can type any
valid python in here.

Put in

    print("hello, world")

To execute it, go up to 'Cell...' and select 'Run'.  You should see the
output (or a syntax error).

You can also edit and rexecute this cell. Try it!

To add a cell, go to Insert and Insert cell below. Now add another statement
and execute it.

Using the menu to execute cell is annoying so you can use CTRL-ENTER
and SHIFT-ENTER.  What's the difference between these?

[//]: # (@@restart kernel etc)
[//]: # (@@execution numbers etc)
[//]: # (@@pulling up a new notebook)

You can also define variables: put a=5, b=10.  Then in another cell put c=a+b
and print(c).  These are persistent definitions with a notebook's namespace.

You may notice that the numbers change a bit. What's up with that?

That's the *execution order*. Later numbers were executed last.  So it's
possible to execute cells in different order, which can get confusing.

Try adding a new cell with a=20. Then execute it. Now re-execute the c=a+b
cell.

The order of execution follows the numbers, not the cell order.  Generally
before saving a notebook you should go run all: Cell menu, Run all.
That will run all the cells in order in the notebook.

Cell output updates in real time. So, if you have long-running cells you'll
see output as it comes.

## Plotting

Probably the single most useful thing for me about notebooks is the plotting,
which also shows up in the notebook.

We'll use the matplotlib plotting. To get started, do:

    %matplotlib inline
    from pylab import *

Now, create a plot:

    x = range(10)
    y = [ i**2 for i in x ]
    plot(x, y)

You can update this plot incrementally, too, of course, so e.g. change
the plot line to 'plot(x, y, label="my line")' and then add a
'legend()' command.

[//]: # ()

One super neat feature of Jupyter is the ability to load code into a
cell from other places.  For example, if we go to [the matplotlib gallery](http://matplotlib.org/gallery.html) and see something we want to work with, you
can load that code into the notebook.  For example, if we like [this plot](http://matplotlib.org/examples/images_contours_and_fields/streamplot_demo_features.html) we can grab it directly like so:

   %load http://matplotlib.org/mpl_examples/images_contours_and_fields/streamplot_demo_features.py

(Here, we copied the source code link.)

This kind of feature is called a "cell magic" and you can see the long
list of options in the [cell magics documentation](https://ipython.org/ipython-doc/3/interactive/magics.html).

(If this returns an error, you may need to add '%matplotlib inline' at
the beginning of the cell OR re-run your notebook. Why?)
   
## Moar features

There's some other nice features for writing code.

You can do tab
completion -- try typing 'pr' and hitting tab. You'll see a popup that
gives you all of the commands that start with 'pr'.

This works for modules, too.  Above, we imported 'time'. Let's take a look
at what's in time by typing 'time.' and then <tab>.

You can also get help - type 'print?' and hit enter.

## Getting in (and out) of trouble

If you want to clear the variables and restart, you can go up to Kernel
and do "restart".  Now try typing 'print(a)' in a new cell.  You'll see
the numbers have reset (and 'a' isn't defined!)

If you get into an infinite loop, or just want to break into a cell,
use Interrupt Kernel.  Try 'import time; time.sleep(15)' and then interrupt
kernel.  Note that the cell number is '*' while it's executing.

It's generally good practice to restart the kernel and execute from the
beginning before saving or continuing a notebook.

[//]: # (@@ cell magics https://ipython.org/ipython-doc/3/interactive/magics.html)

## The menus

So, that's the majority of the notebook features I use myself.  Let's take
a look through the menus.

Help ... keyboard shorcuts.  For example, type 'Escape' to go into command
mode, and then type 'l'. you'll see line numbers for that cell. toggle 'l'
again.

You can also use CTRL-m to go into command mode, and CTRL-m h will give
you the help for keyboard shortcuts.  The main ones I use are ctrl-m a
and ctrl-m b, which insert above and below the current cell.

Kernel we've already seen.

The cell menu we'll revisit in a bit, when we talk about cell types.

Insert is obvious.

View is obvious.

Edit. Notebook metadata.

File is kind of interesting. You can create a new notebook, re-open
the console, copy, rename, etc.  You can also save and checkpoint,
and then return to that earlier checkpoint.  By default, there's only
one checkpoint, but it will never be clobbered by a save.

You can also print preview, download the notebook as a few things
(depending on what's installed), and stop your notebook.

Continuing on tour, we have the usual functions.

The last two are interesting - cell type (currently set to code) and
cell toolbar (currently set to none). We're going to ignore the cell
toolbar for now, but let's take a look at this cell type.

## Markdown cells

By default, cells in notebooks are code cells. But you can also have
markdown cells, that display formatted text; see [this cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet) for more info on all the syntax.

For now, put in

    # this is a heading

    here is some text with *markup*

and change the cell type to 'Markdown'. Now, when you leave the cell, it
renders nicely.

The only things I know about markdown are: titles start with #,
you can *emphasize* or **bold**, and you can add links with [link text](link).
This is a pretty nice way to write text around analysis discussions, rather
than as comments in the cell.

Jupyter Notebook also has some nice extensions for markdown that let you
put in equations, if you're so inclined.  For example, put in:

    $f = \frac{x}{y}$

in a markdown cell and you'll see it render as a nequation.  This uses
[latex symbol notation](http://web.ift.uib.no/Teori/KURS/WRK/TeX/symALL.html).

So, in a notebook, you can intersperse code with text.

That concludes an initial tour of what notebooks can do. Next we'll
talk more about the whole Jupyter Notebook ecosystem. But, if you're
interested in seeing more about what you can do with notebooks,
there's lots of interesting notebooks to look at in the [Jupyter
Notebook
gallery](https://github.com/ipython/ipython/wiki/A-gallery-of-interesting-IPython-Notebooks).
