
[An Introduction to Static Site Generators | DigitalOcean](https://www.digitalocean.com/community/conceptual-articles/introduction-to-static-site-generators)

static site → pages already generated before the page request rather than on demands

a template engine creates templates for common elements that appear across the site; base template is container of placeholders that are then filled and turned into html

content goes inside markdown files

metadata and front matter is handled by a language like YAML, which defines attributes about the content and can be used to apply a specific layout from the templates. this data usually sits at the top of a content file, encapsulated by `---` e.g.

```
---
title: Front Matter Matters
author: Author Name
description: Write out your description here
layout: base.html
---
```

[Introduction to Static Site Generators | Static Web Publishing for Digital Scholarship](https://chrisdaaz.github.io/static-web-scholcomm/tutorials/static-site-generators/#setting-up-your-computer)

> On Windows:
> 
> - Click on the `Start` button
> - Type `cmd` select the search result for the `Command Prompt` program
> 
> This will open your terminal to your `User`’s home directory. Here are three important commands to help you navigate your system:
> 
> `dir`   | **List the contents** of your current directory
> `mkdir` | **Make a new directory** (or folder) called `new-folder` by running `mkdir new-folder`
> `cd`    | **Change directories** to a target folder by running `cd path\to\new-folder` 

SSGs of interest:

* [[Quartz]]
* [[Astro]]