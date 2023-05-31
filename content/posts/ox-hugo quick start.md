+++
title = "Start blogging with hugo and org."
author = ["Prodip Kumar"]
tags = ["org", "hugo", "emacs"]
categories = ["tech"]
draft = false
[cover]
  image = "one.png"
+++

## Create Hugo Site. {#create-hugo-site-dot}

Hugo is a great tool to create static websites, and now with the power of emacs and org mode this can be as easy as Chatting online.
So lets get started.


### Dreaming of Theming {#dreaming-of-theming}

There are many ways to add a hugo theme . Today we are gonna use the go submodule to install theme.

1.  First start a new hugo site with

<!--listend-->

```bash
hugo new site <site name>
cd <site name>
```

1.  There would be a config.toml in that directory. Remove that and create a config.yml file.
    There is an example for config.yml in **papermod** theme [example](https://github.com/adityatelange/hugo-PaperMod/wiki/Installation#sample-configyml), use that for yous sites config.yml.
    Change the example config.yml to your liking. Dont forget to change the base url to the domain name .Add the following lines in the yml file.

<!--listend-->

```yml
module:
  imports:
    - path: github.com/adityatelange/hugo-PaperMod
```

Dont forget to remove this line 'theme: hugo-PaperMod'.

1.  Than run this command, This command is used to download and update papermod theme module.

<!--listend-->

```bash
hugo mod get -u
```

This should install hugo papermod theme as a go module . Make sure you have go language installed in your system.

1.  Though we will be using emacs ox-hugo to write our blogs, but for testing your hugo site we will create a test post and take a look of our website.
    ```bash
       hugo new posts/<postname>.md
    ```
    Than cd into content/posts directory and edit that &lt;postname&gt;.md file. Run 'hugo server' command in the root of the project and open browser localhos:1313 to view your first post.


## Ox-hugo setup . {#ox-hugo-setup-dot}

Now that you have a working hugo site lets get into the emacs part of this game. If you are doom emacs user "like me"  you can simpley
edit your init.el file in your $DOOM_DIR with following .

```elisp
(org +pandoc +hugo)
```
