# webassets-bootstrap

Example project that tries to show best practices for having a customized version
of [bootstrap](http://getbootstrap.com/) within a
[webassets](https://github.com/miracle2k/webassets) project.

# What you get

  * Sample YAMLLoader build of bootstrap, both the Less and Sass versions
  * Both builds show how to use custom variables

# Checking out this repo

Note that this repo uses submodules.

## Cloning it for the first time

    git clone --recursive https://github.com/JDeuce/webassets-bootstrap


## Getting submodules after clone without --recursive

    git submodule update --init --recursive

# Dependencies

## less
### npm

    npm install -g less

### ubuntu

    apt-get install node-less

## sass
### gem

    gem install sass


### ubuntu

    apt-get install ruby-sass

## webassets
### pip

    pip install webassets

### ubuntu

    apt-get install python-webassets

# Running it

A makefile is included for simple operation,
but you could just as easily run webassets manually.

## Building

    $ make
    webassets -c webassets.yaml build
    Building bundle: dist/sass.css
    Building bundle: dist/less.css

## Cleaning

    $ make clean
    webassets -c webassets.yaml clean
    Cleaning generated assets...
    Deleted asset: dist/sass.css
    Deleted asset: dist/less.css

## Did the variables work?

The variable we use sets the navbar-bg-color to #dedbef, the bootstrap
default is #f8f8f8. There should only be 1 reference to either of those colours
in the output:

    $ grep -oE "dedbef|f8f8f8" dist/*
    dist/less.css:dedbef
    dist/sass.css:dedbef

