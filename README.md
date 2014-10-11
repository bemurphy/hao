# hao

Short for "Heroku Addons Open"

## What

Just a little script to make opening addons for an app easier.  Currently
only has shortcuts for papertrail and newrelic because that's what I use
most.

## Prerequisites

You have a system ruby installed.  This doesn't use anything beyond STDLIB

## Conventions

The Heroku apps are named like app-staging and app-production where app is equal to basename $PWD.

`_` in the basename will translate to `-` in the appname as heroku does not permit underscores in names.

## Usage

Given your are in a directory like `$HOME/code/foobar-app`

Shortens this:

```shell
$ heroku addons:open newlic --app foobar-app-production
```

Into this:

```shell
$ hao nr
```

You can also use shortcuts to specific an alternate environment (usually staging):

```shell
$ heroku addons:open papertrail --app foobar-app-staging
$ hao pt s
```

You can be explicit with the addon name:

```shell
$ heroku addons:open papertrail --app foobar-app-staging
$ hao openredis
```
