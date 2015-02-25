---
layout: blog
category: zapisy
splash: "http://placehold.it/1600x500"
title: Jednání komise pro IT
tags: it, komise
---

Yesterday I have upgraded postgress server packages on my server.
It has not started anymore so I have begun searching why.
The log told me that I use data created for old version of postgress.
So the migration journey begun.

The migtration tool [pg_upgrade](http://www.postgresql.org/docs/9.2/static/pgupgrade.html)
wanted several directories as params but after upgade of pg server the "old_bindir" did not exist.
You have downloaded the old packages and extract them to get the "old_bindir":

  DEB_URL=`search google for package for your distro and version`
  wget $DEB_URL -O postgre8.4.deb
  OLD_PACK=/tmp/pg-old
  mkdir $OLD_PACK
  dpkg-deb -R postgre8.4.deb $OLD_PACK

Now you need create 8.4 environment (the configs in /etc/postgres).
Magic tool is used for that:

  . /usr/share/postgresql-common/maintscripts-functions
  configure_version 8.4
