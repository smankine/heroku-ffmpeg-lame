Heroku buildpack: FFmpeg with LAME
==================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [ffmpeg](http://www.ffmpeg.org/) compiled with LAME.

Usage
-----

To use this buildpack you'll first need to set `heroku-buildpack-multi` as your custom buildpack:

    $ heroku config:add BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-multi.git

From here you will need to create a `.buildpacks` file which contains (in order) the buildpacks you wish to run when you deploy:

    $ cat .buildpacks
    https://github.com/smankine/heroku-ffmpeg-lame
    + the other build packs you need such as 
    https://github.com/heroku/heroku-buildpack-nodejs


Deploy your app like usual:

    $ git push heroku master
    ...

You can verify ffmpeg is available by running the following command:

    $ heroku run "ffmpeg -version"
