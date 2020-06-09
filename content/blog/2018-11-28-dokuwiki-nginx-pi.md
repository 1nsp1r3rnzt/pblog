---
title: How to configure Dokuwiki Farm and Animals on Raspberry Pi using Nginx
date: 2018-11-28T19:49:27+00:00
url: /dokuwiki-farm/
header:
  teaser: /assets/images/uploads/2018/11/Dokuwiki-configure-header.png
classes: wide
image:
  path: /assets/images/uploads/2018/11/Dokuwiki-configure-header.png
categories:
  - Reviews
---

DokuWiki is a PHP based software for creating your own Wiki. There are alternatives such as [TiddlyWiki](https://tiddlywiki.com/) , [MediaWiki](https://www.mediawiki.org/wiki/MediaWiki) , and [BookStack](https://www.bookstackapp.com/). 

There are other documentation solutions such as [MkDocs](https://www.mkdocs.org/) which looks great accompanied with [Material Design theme](https://github.com/squidfunk/mkdocs-material).

A Wiki is great for the structured data, especially for a personal knowledge management system. Also, being open-source means you can modify and add a feature on your own.

I tried MkDocs , TiddlyWiki and DokuWiki.

## My Primary requirements

- a text-based file hierarchy - assures that I can move on to the next system easily. 
- Responsive Design for mobile - to access on the go.
- Plugins support along with a lot of plugins -  so I don't waste time building the Wiki instead of using it.
- Easier navigation links Generation - Manual is plain labor.
- Full-text search support - to deal with messy file structure hierarchy.

TiddlyWiki was ruled out as it is a nonlinear single page app which will I felt like information overload.

From the rest, DokuWiki is a full-fledged wiki system while MkDocs is like a plug and play. 

I had a spare Raspberry Pi which is okay for installing Dokuwiki.

For Basic installation on Raspberry Pi 3, I followed this the tutorial on [TechCoil](https://www.techcoil.com/blog/how-to-setup-your-own-wiki-site-on-a-raspberry-pi-3-with-dokuwiki-raspbian-stretch-lite-nginx-and-php/) but got stuck as it did not explain anything about setting up the farm and animals.

> A wiki farm is a collection of wikis running on the same web server and sharing one parent wiki engine. So, by running just one single parent wiki, you can power hundreds of independent other wikis (aka “animals”). All animals share one set of plugins and templates but each of them can have a different set of enabled plugins, a different template, and a different configuration. The concept of farms is also called “multi-site”, “multi-domain” or “sub-sites” in the context of other CMS.

The [official tutorial](https://www.dokuwiki.org/farms) teaches configuring Apache only. It is based on .htaccess which are not supported in Nginx.

First, you need to decide the folder structure for your wiki.

For example,

## Farm Directory Structure

The farm directory can theoretically be anywhere in the file system but we recommend the following structure:

- `/var/www/dokuwiki` – the DokuWiki engine A.K.A the farmer
- `/var/www/farm` – contains all the animals - the farm
- `/var/www/farm/animal1` — one wiki  -  Animal 1
- `/var/www/farm/animal2` — another wiki -  Animal 2

DokuWiki operates under the PHP server permissions which uses the www-data group.

When creating the folder `farm`, you need to provide correct permissions.

```bash
sudo chown -R www-data:www-data /var/www/html/farm
```

It is easy to set up a farm on a DokuWiki farm using the  [farmer plugin](https://www.dokuwiki.org/plugin:farmer). It allows to create, edit or delete an animal.

Once, you set up the farm and animals, you need to set the site configuration rules in `/etc/nginx/sites-enabled/yourwebsite.com` file.

For setting up `yourwikidomain.com`, it would be `/etc/nginx/sites-enabled/yourwikidomain.com`.

Note: The following code block is for the https server. You can follow the [official nginx installation tutorial ](https://www.dokuwiki.org/install:nginx) for basic configuration.  

Also, I have set up the Nice URL rewrite as .htaccess in a configuration which creates links like example.com/!subwiki.

It means all sub-wikis start with `!`. Thus, you need to capture this and rewrite it as below. 

```bash
server {
 # PASTE AFTER LISTEN 443 IN YOUR SERVER BLOCK
   listen 443;
   #
       location ~ ^/! {
        rewrite ^/!(.*?)/(.*) /$2?$args&animal=$1 last;
        rewrite ^/!(.*)$      /?animal=$1 last;

        }

```

Save the file.

Tip:  Don't forget to restart your wiki using  `Sudo systemctl restart nginx.service       `

Using this, you can save recipes in an animal wiki and other data in farmer (main) wiki.
#### Some good example use of DokuWiki 
- A Blog and Wiki at [simardcasanova.net](https://simardcasanova.net/)
- a recipe cookbook at [blessyourhe.art](https://blessyourhe.art/).
