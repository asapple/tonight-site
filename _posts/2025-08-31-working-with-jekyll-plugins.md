---
layout: post
title:  "Working with Jekyll Plugins"
date:   2025-08-31 09:15:00 +0800
categories: jekyll plugins
---

Jekyll has a rich ecosystem of plugins that can extend the functionality of your site. In this post, we'll explore how to use and create plugins for Jekyll.

## What are Plugins?

Plugins are Ruby gems that extend Jekyll's functionality. They can add custom tags, filters, converters, and more. GitHub Pages supports a limited set of plugins for security reasons, but if you're hosting your site elsewhere, you can use any plugin you want.

## Using Plugins

To use a plugin, you first need to add it to your `_config.yml` file:

```yaml
plugins:
  - jekyll-feed
  - jekyll-sitemap
  - jekyll-paginate
```

Then, if you're not using GitHub Pages, you'll also need to add it to your `Gemfile`:

```ruby
group :jekyll_plugins do
  gem "jekyll-feed"
  gem "jekyll-sitemap"
  gem "jekyll-paginate"
end
```

## Popular Plugins

Here are some popular Jekyll plugins:

1. **jekyll-feed** - Generates an Atom feed for your site
2. **jekyll-sitemap** - Automatically generates a sitemap.xml file
3. **jekyll-paginate** - Paginates your posts
4. **jekyll-redirect-from** - Manages redirects for your site
5. **jekyll-seo-tag** - Adds metadata tags for SEO

## Creating Custom Plugins

You can also create your own plugins. Here's a simple example of a custom generator plugin:

```ruby
module Jekyll
  class CategoryPageGenerator < Generator
    safe true

    def generate(site)
      site.categories.each do |category, posts|
        site.pages << CategoryPage.new(site, category, posts)
      end
    end
  end

  class CategoryPage < Page
    def initialize(site, category, posts)
      @site = site
      @base = site.source
      @dir = "/categories"
      @name = "#{category}.html"

      self.process(@name)
      self.read_yaml(File.join(@base, "_layouts"), "category.html")
      self.data["category"] = category
      self.data["posts"] = posts
    end
  end
end
```

## Conclusion

Plugins are a great way to extend Jekyll's functionality without having to write complex custom code. Whether you're using existing plugins or creating your own, they can help you build a more powerful and feature-rich site.