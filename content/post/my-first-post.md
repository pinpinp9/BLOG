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


We have to clone the theme from the creator to apply it. In the command prompt, Type Hugo new site followed by a folder name Move into the new folder, type cd followed by the folder name you just established Next, clone the theme you choose on the Hugo website followed by the directory which is themes/subdirectory

For example:
```
hugo new site myblog
cd myblog
git clone https://github.com/Tazeg/hugo-blog-jeffprod.git themes/jeffprod
```

If there is no error, you will see a new folder appeared in `themes`.


### Configuration

Copy all code either from the original website or `config.toml` in the themes folder. 

Paste the code in the original file `config.toml` which is usually located at the bottom of the folder.


### Write blog posts

Type hugo new post/`file name` 

```
hugo new post/my-first-post.md
```
 

### Render

Run the server in command prompt

```
hugo server
```

There you go! Check it out if the website can run on your server [http://localhost:1313](http://localhost:1313) 

If you want your website to be officially published, you need to either buy a domain name or register a free one via Netlify





