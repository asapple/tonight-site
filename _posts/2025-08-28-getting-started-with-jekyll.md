---
layout: post
title:  "Getting Started with Jekyll"
date:   2025-08-28 10:00:00 +0800
categories: jekyll tutorial
---

Welcome to the second post on our Jekyll-powered blog! In this post, we'll cover the basics of getting started with Jekyll.

## What is Jekyll?

Jekyll is a simple, blog-aware, static site generator. It takes your content, renders Markdown or Textile and Liquid templates, and produces a complete, static website ready to be served by Apache HTTP Server, Nginx or another web server. Jekyll is the engine behind GitHub Pages, which you can use to host sites right from a GitHub repository.

## Installation

To install Jekyll, you'll need Ruby, RubyGems, and a terminal application. Once you have these, you can install Jekyll with:

```bash
gem install jekyll bundler
```

## Creating a New Site

To create a new Jekyll site, simply run:

```bash
jekyll new my-awesome-site
```

This will create a new directory with all the necessary files to get started.

## Building and Serving

To build your site, navigate to the site directory and run:

```bash
bundle exec jekyll serve
```

This will start a local server at `http://localhost:4000` where you can preview your site.

## Structure

A basic Jekyll site usually looks something like this:

```
.
├── _config.yml
├── _data
├── _drafts
├── _layouts
├── _posts
├── _site
├── .jekyll-metadata
└── index.html
```

Stay tuned for more tutorials on Jekyll!