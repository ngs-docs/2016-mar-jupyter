# Other languages: R notebooks

Try starting an R notebook, and executing:

    require(graphics)
    (yl <- range(beaver1$temp, beaver2$temp))
    
    beaver.plot <- function(bdat, ...) {
      nam <- deparse(substitute(bdat))
      with(bdat, {
        # Hours since start of day:
        hours <- time %/% 100 + 24*(day - day[1]) + (time %% 100)/60
        plot (hours, temp, type = "l", ...,
              main = paste(nam, "body temperature"))
        abline(h = 37.5, col = "gray", lty = 2)
        is.act <- activ == 1
        points(hours[is.act], temp[is.act], col = 2, cex = .8)
      })
    }
    op <- par(mfrow = c(2, 1), mar = c(3, 3, 4, 2), mgp = 0.9 * 2:0)
     beaver.plot(beaver1, ylim = yl)
     beaver.plot(beaver2, ylim = yl)
    par(op)

Basically it all works as you'd expect...

# Moar magic inside notebooks
 
Commands:

    ls, cd, !, tab completion
    %lsmagic

[A list of magics](http://jupyter.cs.brynmawr.edu/hub/dblank/public/Jupyter%20Magics.ipynb)

# Console

Basically, you can interact with the file system in a variety of ways:
via notebook and/or running code, OR via console/upload/download/edit,
OR via terminal.

* upload files;
* download and edit files;
* save and download figures;
* terminal window;

# Sharing notebooks via github

[GitHub](http://github.com/) renders Jupyter Notebooks on their site
-- see
[this](https://github.com/ngs-docs/2016-mar-jupyter/blob/master/my%20first%20notebook.ipynb)
for example.

To try this,

1. Download your notebook from your running Jupyter site.

2. Go to github.com and create a new repository.

3. Select the 'README' link at the top of the new repository.

4. Enter something, click commit.

5. Select "upload files", and upload your downloaded notebook.

6. If you click on the ipynb file in your repository you will now see
   your rendered notebook. This is something you can send to collaborators
   etc.

# Distributing executable notebooks with github and mybinder

But wait! There's more!

On public repositories, you can feed this github URL into mybinder.org and
actually get it running -- try it!

* Go to [mybinder.org](http://mybinder.org) and enter the URL of your github
  repo, then click "make my binder".

* wait a minute, then click "launch binder".

* voila, you're at your github repo - but executing it.

# Wait, where the heck is this all running?

(Discuss the architecture of Jupyter Notebooks)

# Other cool notebook ideas: really interactive blog posts

See [Tim Head's demo](https://betatim.github.io/posts/really-interactive-posts/)

# Other topics

* comparison with RStudio, RMarkdown
* running on your laptop; running on AWS

(**Everything we've done** in the notebook can be done on your laptop -- you
just have to install things ;).

[Return to index](https://github.com/ngs-docs/2016-mar-jupyter)
