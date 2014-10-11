# hao

Short for "Heroku Addons Open"

## What

Just a little script to make opening addons for an app easier.  Currently
only has shortcuts for papertrail and newrelic because that's what I use
most.

## Prerequisites

You have a system ruby installed.  This doesn't use anything beyond STDLIB

You have [Heroku Toolbelt](https://toolbelt.heroku.com/) installed and in your path

## Conventions

The Heroku apps are named like app-staging and app-production where app is equal to basename $PWD.

`_` in the basename will translate to `-` in the appname as Heroku does not permit underscores in names.

## Installation

Copy `hao` into your local bin directory ($HOME/scripts, $HOME/bin, whatever).  chmod 755 it.

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

Since the environment was not provided, it assumed production.

You can also use shortcuts to specific an alternate environment (usually staging):

```shell
$ heroku addons:open papertrail --app foobar-app-staging
$ hao pt s
```

You can be explicit with the addon name:

```shell
$ heroku addons:open openredis --app foobar-app-production
$ hao openredis
```
