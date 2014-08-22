# Kalabox Plugins
===============

This will be the canonical repository for what kalabox plugins will look like

## Plugin Types

### Component 

This would be a single service like mysql. It would include the location of an image or eventually a docker build location. In the future build use case we would also include some configuration we would want to customize things like php_memory_limit. We prob want to separate them out in to specific folders like "data, webserver, db, index, keyvalue, php". This is also a special component called "omni" that which is a container that contains many services a la kalastack-docker. 

These plugins should contain the metadata to be passed into `docker run` or `docker build`. 

### Profile: 

This would be a combination of docker components designed to mock a some environment, ie a "acquia profile". It would basically just match a certain role ie `webserver` or `database` to a particular component plugin. 

### Project: 

This would be a description of a certain kind of application starting point that can be instantiated by Kalabox like Drupal 7 or Panopoly or Wordpress. The location of the source/downloads and then a "default" profile for the project to run in. This could be a ref to a docker profile or a bunch of components listed as either required or optional, there should also be a "swappable" binary that would let the user choose a different docker profile or mix and match components.

When a user selects to build a particular application it should contain the metadata and links to other plugins so Kalabox can build the underlying docker containers plus the actual application. These are only used when the user starts a "new" project ie one that is not taken from pantheon or elsewhere. 

### Switchboard

The authentication requirements for a given provider, able to be rendered into a form on the Angular side. 
