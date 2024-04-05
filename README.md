---
title: readme_to_devto README.md
description: (Optional) description
tags: 'optional, tag'
cover_image: ./assets/cat.jpg
published: false
---


***

Some random text with a [link](https://code.visualstudio.com).

## Serious title

Add some text here and there!

![and some pictures too](./assets/cat.jpg)

***

Notes:
* Based on: https://github.com/sinedied/publish-devto 
* The content above is modified from: https://github.com/sinedied/devto-github-template/tree/main/posts
* GitHub repo `Settings` -- `Actions | General` `Workflow permissions` set to `Read and write permissions`
* GitHub repo `Settings` -- `Secret and variables | Actions` new `Repository secrets` `DEVTO_TOKEN` 
* Seems only work for public repo
* Concerning above *post metadata*:
  - `title` seems should be set correctly the first time, and should not be changed
  - `description` is optional (i.e can be missing)
  - `tags` is optional; a list of comma-delimited single-words
  - `cover_image` is optional
  - `published` set to `true` to publish the post
  - the first successful trigger of workflow, `id` will be added automatically (`README.md` modified in the repo, and need be pulled)





