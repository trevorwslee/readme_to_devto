---
title: GitHub Repository README to DEV Community Post
description: Setup GitHub repo for automatically posting README to DEV Community  
tags: 'github, readme, devto'
cover_image: ./assets/cat.jpg
published: false
---


# GitHub Repository README to DEV Community  Post


The enabler is a GitHub Action workflow contributed by the [publish-devto](https://github.com/sinedied/publish-devto) project

Hence, the picture

![cat.jpg](./assets/cat.jpg)

which is the sample that comes with the `publish-devto` project. 

Here I will simply show how I setup GitHub repo for automatically posting README (`README.md`) to DEV Community (`dev.to`).

## On Dev Community Side

As expected, you will need some "access token" from `dev.to` for the workflow to work.

Indeed, you will need to get an API token (`DEVTO_TOKEN`) -- `Settings` -> `Extension` -> `DEV Community API Keys`

![dev_api_key.png](assets/dev_api_key.png)

## On the GitHub Repo Settings Side

Firstly, grant "read and write permissions" to "Workflow" -- `Settings` -> `Actions | General` -> `Workflow permissions` set to `Read and write permissions`

![rw_permit.png](assets/rw_permit.png)

Secondly, setup `DEVTO_TOKEN` secret -- `Secret and variables | Actions` new `Repository secrets` `DEVTO_TOKEN` 

![set_secret.png](assets/set_secret.png)

## On Repo Source Side

Firstly, you will need `.github/workflows/publish.yml` that you can download [here](https://github.com/trevorwslee/readme_to_devto/blob/main/.github/workflows/publish.yml),
which is one that I modified from the one that comes with the `publish-devto` project

Secondly, your `README.md` will need to have *headers* (starting from 1st line) like

```
---
title: GitHub Repository README to DEV Community Post
description: Setup GitHub repo for automatically posting README to DEV Community  
tags: 'github, readme, devto'
cover_image: ./assets/cat.jpg
published: false
---
```

Notes on the *headers*:
- `title` should be set correctly the first time, and should not be changed (unless you want to start a new post)
- `description` is optional (i.e can be missing)
- `tags` is optional, which is a list of comma-delimited single-words
- `cover_image` is optional
- `published` should be `false` until you want to publish the post
- the first successful trigger of the `publish` workflow, `id` will be added automatically (`README.md` modified in the repo, and need be pulled)
  without the `id`, post will be treated as a new post


That is it. Commit the changes to your repo, you should see the running of the workflow `publish`.

If the workflow is successful, a new draft post will be created on Dev Community (`dev.to`)

![workflow.png](assets/workflow.png)

Be reminder that is the is the first time successful running of the workflow, `id` will be created and `README.md` will be modified. Pull the change.












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





