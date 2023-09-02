# knoWLEDge

The official documentation page for the WLED project!  
[To live page](https://kno.wled.ge)
  
Community improvements are encouraged! Just click the little pencil mark on the page you'd like to change and submit a pull request.  
If you'd like to do more advanced changes (e.g. adding a page), the [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/getting-started/) is very helpful.

### Images

If possible, it is preferable to store image content within this repository at `/docs/assets/images/content`. With external links, there is always a chance that the resource is deleted accidentally by the external hoster.

### How to add a new page

Let’s consider an example. Let’s imagine we want to add a page called `Top 5 mistakes` in section `Basics` after the `Getting Started` page. This page already exists, so you can already see the results in WLED Docs, but let’s imagine the page is not there and we will go steps needed to add it:

1)	Create a file that should contain the documentation. As we want to place the new page in section `Basics` it makes senso to put this file in subfolder `docs/basics/`. In our example we call the file `top5_mistakes.md`. You can use another .md file as an example. Important is to have the following few lines at the beginning of the file:
```
---
title: TOP 5 mistakes
hide:
  # - navigation
  # - toc
---
```
Don’t forget to adapt the title.

2)	Edit `mkdocs.yml` file. Take care that indentations play an important role in .yml files. Go to `nav:` section in this file and add a new line after the line `- Getting Started: basics/getting-started.md` as we want to add or new page after the `Getting Started` page. The new line must have the same indentation as the previous line and the content is `- Top 5 mistakes: basics/top5_mistakes.md`. By this we say that the new page must be called `Top 5 mistakes` and its content is in the file `top5_mistakes.md` we created before in subfolder `basics`.
That is!

### How to add a new section

It is even easier. Take a look at `nav:` section in `mkdoks.yml` file. To add a new section you just have to add a new line at a position where the new section must be. Then write a section name like this: `- Compatibility:`. TAKE CARE on indentations! After this line you can then add new pages as described above.

### How to test the representation of the documentation in web locally (on Windows, MAC OS X or Linux)

You would need to install some tools:

1) WEB Server. The probably easiest way is to use [XAMPP](https://www.apachefriends.org/index.html) to run local WEB server on your PC/Laptop. After installing you would need to start XAMPP Control Panel and run Apache Server. In the folder where XAMPP is installed to you will find a subfolder called `htdocs`. This is the content of the WEB Server and you have to put WLED DOCs web pages there, for example in subfolder called `wled-docs`. Later after generating pages using mkdocs you will be able to access them via `http://localhost/wled-docs/site/`
2) [Python](https://www.python.org/)
3) [MkDocs](https://www.mkdocs.org/user-guide/installation/#mkdocs-installation)

Now you can downlaod WLED Docs sources from the repository to subfolder `wled-docs` in the folder `htdocs` in your XAMPP installation. To "compile" the resulting web pages you have to run `mkdocs build` command in the `wled-docs` folder using command line. It generates subfolder 'site' with the resulting web pages and you can access them in your browser via `http://localhost/wled-docs/site/`
