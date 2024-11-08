# LocoMotion Buildpack for Heroku

This Buildpack helps Heroku build the LocoMotion demo site by configuring it to
use a local version of the LocoMotion gem.

It is based off of the
[subdir-heroku-buildpack](https://github.com/timanovsky/subdir-heroku-buildpack/).

## Usage

The main / useful file is `bin/compile` which copies the `docs/demo`
subdirectory to the correct place, and also copies the relevant LocoMotion gem
files into the `docs/demo/vendor/loco_motion-rails` directory where the demo
application expects it to live.

Make sure that this buildpack comes **first** in your list so that the files
will be in the correct places when your Node / Ruby buildpacks run.

## Why?

For local development, this is done with Docker volumes, but we need a different
solution for Heroku.
