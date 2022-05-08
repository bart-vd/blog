---
title: "First Steps With Hugo"
date: 2022-04-19T11:40:37+02:00
draft: false
tags: ["blogging", "hugo"]
---
First things first: before anything else, I had to install the [Hugo](https://gohugo.io) static site generator, which is going to be the main tool for building the site. In this post, I discuss installing Hugo, and creating a new Hugo site, _and_ we go through the most important folders, explaining what they are for.

## Installing Hugo

Since I'm on Mac, this is kind of trivial when you have the fantastic [Homebrew](https://brew.sh) installed. Homebrew is a MacOS package manager (analogous to [apt](https://wiki.debian.org/Apt) in Debian Linux for instance), which allows you to install Mac software from the command line easily. For installing Hugo, the command is:

```bash
$ brew install hugo
```

To verify whether the installation was succesful, type:

```bash
$ hugo version
```

Which should result in something like `hugo v0.97.2+extended darwin/amd64 BuildDate=unknown`.

## Create a Hugo site

Next, creating the basics for a Hugo site is as simple as typing:

```bash
$ hugo new site blog
```

This creates a folder called `blog` which contains a number of files and folders necessary for creating a Hugo site:

```bash
$ ls
archetypes  config.toml  content  data  layouts  public  static  themes
```

## The folder structure

### /archetypes

When you use the `hugo new` command to create new content, Hugo creates new [Markdown](https://www.markdownguide.org) content files, based on _archetypes_. These archetypes contain custom preconfigured elements (like title and date) and [frontmatter](https://gohugo.io/content-management/front-matter/). Archetypes save time and promote consistancy for sites using multiple content types.

### /config

Hugo ships with a large number of configuration directives. The `config` directory is where those directives are stored as JSON, YAML, or TOML files. Projects with minimal settings can use a single `config.toml` file at its root. Many sites may need little to no configuration, but Hugo ships with a large number of [configuration directives](https://gohugo.io/getting-started/configuration/#all-configuration-settings) for more granular control on how you want Hugo to build your website.

### /content

All content for your website will live inside this directory. Each top-level folder in Hugo is considered a content section. For example, if your site has three main sections — blog, articles, and tutorials — you will have three directories at content/blog, content/articles, and content/tutorials. **Hugo uses sections to assign default content types**.

### /data

This directory is used to store configuration files that can be used by Hugo when generating your website. You can write these files in YAML, JSON, or TOML format. In addition to the files you add to this folder, you can also create data templates that pull from dynamic content.

### /layouts

The `layouts` folder stores templates in the form of `.html` files that specify how views of your content will be rendered into a static website. Templates include list pages, your homepage, taxonomy templates, partials, single page templates, and more.

### /static

`static` stores all the static content: images, CSS, JavaScript, etc. When Hugo builds your site, all assets inside your static directory are copied over as-is.

### /resources

The `resources` directory caches some files to speed up generation. It can be also used by template authors to distribute built SASS files, so you don’t have to have the preprocessor installed. The resources directory is not created by default.

### /assets

The `assets` folder stores all the files which need be processed by Hugo Pipes. Only the files whose .Permalink or .RelPermalink are used will be published to the public directory. Note: assets directory is not created by default.
