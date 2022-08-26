---
toc: true
layout: post
description: Serving fastpages locally using docker.
categories: [markdown]
title: Docker server
---

It's often useful to test pages locally before deploying, as it can save time and be helpful for testing quick changes/debugging. In this blog we'll learn how to deploy fastpages locally using Docker.

## Overview of steps

1. Download Docker desktop
2. (For Windows) Set up Docker with WSL
3. Run `make server` in repo
4. Navigate to https://127.0.0.1:4000/ to view your blog

### Installation

Docker is a lightweight method to build, deploy, run, update and manage containers. Download Docker desktop from following links:

Windows: https://docs.docker.com/desktop/install/windows-install/
Mac: https://docs.docker.com/desktop/install/mac-install/.

#### Special steps for Windows

For Windows, to set up Docker with WSL use https://docs.docker.com/desktop/windows/wsl/.

### Docker command

In the local repository, make sure you are cd'ed to the base/root directory (i.e. where the Makefile is). For me that was the ap-csa-fastpages directory.

![image](https://user-images.githubusercontent.com/56745453/186964001-45e37d26-45b0-484d-bac6-b85b67cb2ffb.png)

The Makefile contains common aliased commands for building and serving your fastpages locally. If you look inside the file or run `make` in terminal, you can see what docker commands it is running.

![image](https://user-images.githubusercontent.com/56745453/186964281-4c238041-0e9e-4319-affa-5d0aebe084b3.png)

Specifically, we are interested in the `make server` command, which will build the container the first time and start the Jekyll server. If you remember from AP CSP, Jekyll is what powers Github pages behind the scenes. You can build your GitHub Pages site locally using Jekyll to preview and test changes to your site.

#### Special steps for Windows

The first time, you might get this issue:

![image](https://user-images.githubusercontent.com/56745453/186963057-bb16c926-33f5-41cb-abe1-65886678f477.png)

If that's the case, make sure this setting is toggled on in Docker desktop settings:

![image](https://user-images.githubusercontent.com/56745453/186963251-602a4073-caab-40ca-8441-55be64d9c7f7.png)

It should ask you to reload and if you run the command again it should work now.

### Resources

https://github.com/fastai/fastpages/blob/master/_fastpages_docs/DEVELOPMENT.md
