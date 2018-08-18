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
 - `hexo g` generate
 - `hexo d` deploy to git
 - `hexo clean`



