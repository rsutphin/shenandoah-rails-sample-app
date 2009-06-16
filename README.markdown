ScalaEnvy (Shenandoah Rails Sample App)
=======================================

Welcome to the Rails sample application for [Shenandoah][]. Shenandoah is a JavaScript testing metapackage for projects built with ruby-based tools.  It can be used with any project that builds with `rake` or `buildr`. 

As Shenandoah is a generalization of the [Blue Ridge][blue-ridge] rails plugin, this application is a modification of Blue Ridge's [sample app][blue-ridge-sample] to work with Shenandoah.

This sample application demonstrates: 

* configuring in the shenandoah gem 
* using nested `describe` functions
* setting up per-spec HTML "fixtures"
* stubbing functions
* mocking functions
* running the Shenandoah specs as part of your default Rake task

To verify that all the tests pass, clone the repo and follow the instructions below.

[shenandoah]: http://github.com/rsutphin/shenandoah
[blue-ridge]: http://github.com/relevance/blue-ridge
[blue-ridge-sample]: http://github.com/relevance/blue-ridge-sample-app

Noteworthy Bits
---------------

* public/javascripts/project.js: the JavaScript code used to power the app's client-side interactivity
* test/javascript/project\_spec.js: the specs for the JavaScript code present in public/javascripts/project.js
* test/javascript/spec\_helper.js: the helper code used by project\_spec.js and available to any other JavaScript specs you might define for the app

Installing and Running
----------------------

To install:

    gem install shenandoah          # you might need to sudo here
    git clone git://github.com/rsutphin/shenandoah-rails-sample-app.git shen-scalaenvy
    cd shen-scalaenvy
    cp config/database.sample.yml config/database.yml
    rake db:migrate

To run all of the JavaScript specs:

    rake shen:spec

To run *all* of tests (i.e., Ruby *and* JavaScript):

    rake

To run the application:

    script/server 

The sample app should now be running at http://localhost:3000

Notes
-----

This sample app uses jQuery exclusively, but Shenandoah plays nicely with Prototype as well.  Check out the [Shenandoah README][shenandoah] for an example of testing JavaScript that relies on Prototype.
