---
title: "Create your own website for free by HUGO "
date: 2020-08-11T18:23:44+10:00
archives: "2020"
tags: [
    "hugo",
    "webpage",
    "website",
    "theme"    
]
author: Pinpinqi
---


### Install Hugo on your device 




If you are on macOS or linux and using [homebrew](https://brew.sh/), you can install Hugo with the following one-liner:

```
brew install hugo
```

If you are on a Windows machine and use [Chocolatey](https://chocolatey.org/install) for package management, you can install Hugo with the following one-liner:

```
choco install hugo -confirm
```

After installation is done then choosing Hugo themes -- https://themes.gohugo.io/



### Cloning the theme to create your own website




Hugo new site follow by a folder name you want to create


Move into the folder and clone the theme you choose with git command.


For example:
```
hugo new site myNewWebSite
cd myblog
git clone https://github.com/Tazeg/hugo-blog-jeffprod.git themes/jeffprod
```
If everything is alright, you will see a new folder appeared in `themes`.

Find a file `config.toml` in themes folder. 

Copy all code and paste in the original `config.toml` file which is usually located at the bottom of the folder.

Run the server in command promt

```
hugo server
```

There you go! Check out if the website can run on your server [http://localhost:1313](http://localhost:1313) 

<!-- ![theme](/img/hugo-theme.jpg) -->



