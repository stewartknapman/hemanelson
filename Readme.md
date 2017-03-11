# HEMA Nelson

Official website for HEMA Nelson: [http://www.hemanelson.com](http://www.hemanelson.com)

This site is a static HTML site built with [Jekyll](https://jekyllrb.com/) and hosted by [GitHub Pages](https://pages.github.com/).

## Updating content

Jekyll uses [Markdown](#markdown) (plain text) files and converts them into HTML.

![Jekyll is MAGIC!](https://m.popkey.co/e74327/ZLXZR.gif)

There are two ways to update the sites content: the first is through the [GitHub web UI](#github-web-ui); the second is [locally](#local-content-editing), and then push the changes with Git.

Using the web UI is great if you want to make small quick changes, or purely text based changes.

Using the local dev method is recommended if you want to use your own tools, or add images, PDF's, or any other kind of asset. (Assets _can_ be added via the web UI, but is probably easier done locally, so this becomes personal preference).

### Jekyll page files and folder structure

To create a new page you can make a new file with the suffix `.html`, `.markdown`, or `.md`. This will be converted into an html file ready to be served by the site.

For pages within sub directories i.e. `hemanelson.com/path/to/page.html` just create the directory into the sites root folder and include your Markdown file i.e. `./path/to/page.md`.

_It is important to note_ that the file created can contain the following triple-dashed lines at the very top of the file:

```
---
---
```

You should include a title for your page like so:

```
---
title: My awesome page title
---
```

The site won't break if this is not included, but it's good practice.
For more information on this refer to [Jekyll's guide to front matter](https://jekyllrb.com/docs/frontmatter/).

### Markdown

Regardless of the file suffix you use you can use a mixture of Markdown and HTML in your content.

[Refer to this Markdown cheat-sheet for more information](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

### GitHub web UI

Editing files via the web UI will run the site builder automatically once the changes have been committed. It will take a minute for the new files to be built and for the sites cache to be updated, but any changes should be visible on the live site shortly after update.

### Local content editing.

#### Getting started

To edit the content locally you first have to clone down the sites repository with Git. This only needs to be done once, the first time you work with the site:

```
git clone https://github.com/stewartknapman/hemanelson.git
```

#### Pulling down remote changes

If changes have been made via the web ui or by other people you will want to make sure that your local site is up-to-date. **This should be the first thing you do every time you start working on the site locally**.

```
git pull
```

If this is the first time working on the site and you have just run `git clone ...` then you won't need to do this.

#### Committing and pushing changes

After making your changes you will need to run the following commands. This needs to be done each time, when you are ready to submit your changes:

_Add the changes to git locally and give the commit a message_
```
git add -A && git commit -m '[quick message explaining changes]'
```

_Push the changes to the remote repository_
```
git push
```

#### Viewing site updates locally

It's possible to view the sites changes, served locally, inside your browser before pushing them to GitHub. However this requires installing Ruby and the Jekyll gem.

This is covered by the [building locally section](#building-the-site) of this guide.

## Building the site

Building locally allows you to update the Jekyll templates (HTML & Liquid), CSS, and Javascript. Or just to preview the site before pushing any changes to GitHub to be served.

**If all you want to do is work with the content and don't care about the HTML, CSS, etc. then there is no need to read any further.**

### Set up

You will first need to install [NodeJS](https://nodejs.org/en/) and [Ruby](https://www.ruby-lang.org/en/) to be able to run the build tools for the site. You should refer to these sites installation guides.

Once these are installed you will want to install the dependancies relevant to this site.

To install Jekyll and its dependancies run:
```
bundle install
```

Next install the Node dependancies:
```
npm install
```

With any luck this should all Just Work&trade;

### Building

To run everything use the following command. You will need to do this once at the beginning when you make you changes:

```
npm run build
```

This will:
- Run a local server and open a new browser window for the compiled site.
- Set up watchers to recompile the site and update the browser window (no need for page refresh) when any sites file is created or changed.
- Run SASS and Javascript build tasks and add them to the site when assets sources are updated.
