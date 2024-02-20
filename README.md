# knoWLEDge

The official documentation page for the WLED project!  
[To live page](https://kno.wled.ge)
  
Community improvements are encouraged! Just click the little pencil mark on the page you'd like to change and submit a pull request.  
If you'd like to do more advanced changes (e.g. adding a page), the [Material for MkDocs documentation](https://squidfunk.github.io/mkdocs-material/getting-started/) is very helpful.

### Images

If possible, it is preferable to store image content within this repository at `/docs/assets/images/content`. With external links, there is always a chance that the resource is deleted accidentally by the external hoster.

### How to add a new page

Let’s consider an example. Let’s imagine we want to add a page called `Top 5 mistakes` in section `Basics` after the `Getting Started` page. This page already exists, so you can already see the results in WLED Docs, but let’s imagine the page is not there and we will go over the steps needed to add it:

  1. Create a file that should contain the documentation. As we want to place the new page in section `Basics` it makes sense to put this file in subfolder `docs/basics/`. In our example we call the file `top5_mistakes.md`. You can use another .md file as an example. Important is to have the following few lines at the beginning of the file:
     ```
     ---
     title: TOP 5 mistakes
     hide:
       # - navigation
       # - toc
     ---
     ```
     Don’t forget to adapt the title.

  2. Edit `mkdocs.yml` file. Take care that indentations play an important role in .yml files. Go to `nav:` section in this file and add a new line after the line `- Getting Started: basics/getting-started.md` as we want to add a new page after the `Getting Started` page. The new line must have the same indentation as the previous line and the content is `- Top 5 mistakes: basics/top5_mistakes.md`. By this we say that the new page must be called `Top 5 mistakes` and its content is in the file `top5_mistakes.md` we created before in subfolder `basics`.

That's it!

### How to add a new section

It is even easier. Take a look at `nav:` section in `mkdoks.yml` file. To add a new section you just have to add a new line at a position where the new section must be. Then write a section name like this: `- Compatibility:`. TAKE CARE on indentations! After this line you can then add new pages as described above.

### How to test the representation of the documentation in web locally (on Windows, MAC OS X or Linux)

The easiest way to preview the documentation locally is with Docker, but you can also do it by installing mkdocs-material with Python. We'll outline both options below. In either case, you'll need a local copy of this repository to work with (either via `git clone https://github.com/Aircoookie/WLED-Docs` or by downloading the sources).

#### Run Locally with Docker

You must have [Docker](https://www.docker.com/products/docker-desktop/) installed. From a terminal in the `WLED-Docs` folder, run:

```
docker run --rm -it -p 8000:8000 -v ${PWD}:/docs squidfunk/mkdocs-material
```

The docker container builds and serves the site. You can see it at <http://localhost:8000>. Use <kbd>Ctrl-C</kbd> to stop the server. See the [mkdocs-material documentation](https://squidfunk.github.io/mkdocs-material/creating-your-site/#previewing-as-you-write) for more info.

#### Run Locally with mkdocs

1. You must have [Python](https://www.python.org/) installed.
2. Building the docs requires [mkdocs-material](https://squidfunk.github.io/mkdocs-material/getting-started/). This can be installed with pip or [pipx](https://github.com/pypa/pipx).
3. From the `WLED-Docs` directory, run `mkdocs serve`. This will build the site and serve it. View the site at <http://localhost:8000>.
