---
title: Beautify your github pages with Hexo
p: hexo/
tags: Hexo
categories: Hexo
comments: true
date: 2018-01-25 20:48:39
---

**Install local git**

**Install node.js**

## Create github pages ##

- Apply a github account
- Create a repository, name: [yourGithubAccount].github.io
- Generate github public ssh key with git bash

    ``` bash
    ssh-keygen -t rsa
    ```
- Create new SSH key on github.com. SSH and GPG keys => new SSH key => copy the content of id_rsa.pub generating from the last step
  
- Set global config

    ``` bash
    $ git config --global user.name "[yourName]"//account
    $ git config --global user.email  "[yourEmail]"//Email
    ```
---


## Install and Config Hexo ##

#### create an empty diretory and run 

``` bash
$ npm install -g hexo-cli
$ npm install hexo --save
$ hexo init
```
---

#### some plugins

``` bash
npm install hexo-generator-index --save
npm install hexo-generator-archive --save
npm install hexo-generator-category --save
npm install hexo-generator-tag --save
npm install hexo-server --save
npm install hexo-deployer-git --save
npm install hexo-deployer-heroku --save
npm install hexo-deployer-rsync --save
npm install hexo-deployer-openshift --save
npm install hexo-renderer-marked@0.2 --save
npm install hexo-renderer-stylus@0.2 --save
npm install hexo-generator-feed@1 --save
npm install hexo-generator-sitemap@1 --save
```
---


#### Success

 - generate public diretory

    ``` bash
    hexo g
    ```

 - run on local
 ``` bash
hexo s
 ```
 ---


#### Config on `_config.yml`

```
deploy:
  type: git
  repository: git@github.com:[yourGithubAccount]/[yourGithubAccount].github.io.git
  branch: master
```
---

#### some command
 - `hexo new "title"` post article
 - `hexo new page "articles"` create dir
 - `hexo g` generate
 - `hexo d` deploy to git
 - `hexo clean`


> visit url: https://luohanqun.github.io/


## Change Theme

#### In Console
```
$ cd root-dir-for-hexo-blog
$ yarn
$ git clone https://github.com/mkkhedawat/clexy themes/clexy
$ yarn remove hexo-renderer-ejs
$ yarn add hexo-renderer-jade
$ yarn add hexo-prism-plugin
```
#### In root's _config.yml :

- Change your `theme` variable to `clexy`
- Add `prism_plugin` options
```
prism_plugin:
  mode: 'preprocess'    # realtime/preprocess
  theme: 'default'
  line_number: false    # default false
```
- Make sure that default code `highlight` plugin is disabled.
```
highlight:
  enable: false
```

## Post Variables

- Add the `intro` variable to your YAML in your Markdown file.
- Comments can be toggled with the `comments` boolean variable.
- Add tag to post using `tags` variable.

```md
---
title: 'Title Name'
date: 2017-06-01 21:56:56
tags:
- tag1
- tag2
intro : 'Enter intro here to display on home page'
comments: false
---
```

## Optional Config
- To configure about author page , add following tags in root's `_config.yml`. Remove the config key, you don't want.
```
about : {
  name : "Manish Kumar Khedawat",
  intro1 : "Full Stack Developer, Bosch",
  intro2 : "Alumni'14, IIT Kharagpur",
  linkedin : "https://in.linkedin.com/in/mkkhedawat",
  facebook : "https://www.facebook.com/mkkhedawat",
  twitter : "https://twitter.com/mkkhedawat",
  instagram : "https://www.instagram.com/mkkhedawat/",
  email : "writetomansa@gmail.com",
  github : "https://github.com/mkkhedawat",
  stackoverflow : "https://stackoverflow.com/users/1608029/mkkhedawat",
  sourceforge : "https://sourceforge.net/u/mkkhedawat/profile/"
}
```
- Add `author` and `keywords` meta tag in root's `_config.yml` to be included for header file
```
author: Manish Kumar Khedawat
keywords: "pen, notes, coding, developer"
```

## Booting up blog
```
$ hexo new page "articles"
$ hexo new page "author"
$ hexo new post "Title-1"
$ hexo new post "Title-2"
```
Add content and post variables to both posts, Later
```
$ hexo clean
$ hexo server
```
Open browser and navigate to http://localhost:4000/


