# noshp.github.io
This is a Pelican blog made from jupyter notebooks, html, and md files.
It was made mostly using this reference: https://www.dataquest.io/blog/how-to-setup-a-data-science-blog/

## Getting Started
**Clone the Repo**
```
git clone https://github.com/noshp/noshp.github.io.git
```
cd into the project folder
Have `virtualenv` installed on your machine (http://docs.python-guide.org/en/latest/dev/virtualenvs/)
Activate your virtualenv

*On Mac/Linux:*
```
source venv/bin/activate
```

*On Windows:*
```
venv\Scripts\activate.bat
```
---
## Local Testing
Use the `dev` branch for local testing.

**Create Content**
*Articles* are chronological content (like a blog posts) created by adding HTML, Jupyter Notebook, or Markdown files to the /content folder
*Pages* are content that doesn't change often (like an "About" or "Contact" sections)

All of these require metadata, as follows:

1. HTML
```
<html>
    <head>
        <title>My super title</title>
        <meta name="tags" content="thats, awesome" />
        <meta name="date" content="2012-07-09 22:28" />
        <meta name="modified" content="2012-07-10 20:14" />
        <meta name="category" content="yeah" />
        <meta name="authors" content="Alexis Métaireau, Conan Doyle" />
        <meta name="summary" content="Short version for index and feeds" />
    </head>
    <body>
        This is the content of my super blog post.
    </body>
</html>
```

2. Markdown
```
Title: My super title
Date: 2010-12-03 10:20
Modified: 2010-12-05 19:30
Category: Python
Tags: pelican, publishing
Slug: my-super-post
Authors: Alexis Metaireau, Conan Doyle
Summary: Short version for index and feeds

This is the content of my super blog post.
```

3. Jupyter Notebook
Copy the notebook into the /content folder
Additionally, add a `.ipynb-meta` file with the same name. It should be structured like this:
```
Title: First Post
Slug: first-post
Date: 2016-06-08 20:00
Category: posts
Tags: python firsts
author: Vik Paruchuri
Summary: My first post, read it to find out.
```

---
**See Content**
Once content is added to the /content folder, we can generate the HTML by:
```
cd <your_project_directory>
pelican content
```

We can see the content on our local machine by:
```
cd output
python -m pelican.server
```
You should be able to preview the blog on your browser, at localhost:8000

---
**Push Changes to GH Pages**
Changes to the workign environment are stored on the `dev` branch
Changes to the blog's HTML are stored on the `master` branch

To update the `master` branch:
Ensure that ghp-import is installed
```
pip install ghp-import
```

Send the /output folder's contents to the `master` branch:
```
ghp-import output -b master
git push origin master
```