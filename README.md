# Kalabox Plugins

This will be the canonical repository for what kalabox plugins will look like

## Plugin Types

### Component:

This would be a single service like mysql. It would include the location of an image or a docker build location. In the future build use case we would also include some configuration we would want to customize things like php_memory_limit. We prob want to separate them out into specific folders like "data, webserver, db, index, keyvalue, php".

**Application Component**

A server running something like php-fpm.

**Data Component**

A busybox container used to house the data for your project so as to decouple the project from the underlying archicture. This usually will just be an empty container but could also contain application start states like Drupal 7, Panopoly or Wordpress.

**Database Component**

A server running something like mariadb or mysql.

**Webserver Component**

A server running something like apache or nginx.

### Profile:

This would be a combination of docker components designed to mock a some environment, ie a "acquia profile". It would basically just match a certain role ie `webserver` or `database` to a particular component plugin. This plugin should also contains the metadata to pass to `docker run` or `docker build` so we can spin up the whole situation.

### Project:

This would be a description of a certain kind of application starting point that can be instantiated by Kalabox like Drupal 7 or Panopoly or Wordpress. It would includ the location of the source/archive/ (or maybe a data component) and then the "default" profile plugin for the project to use. This could be a ref to a docker profile or a bunch of components listed as either required or optional, there should also be a "swappable" binary that would let the user choose a different docker profile or mix and match components.

### Switchboard:

The authentication requirements for a given provider, able to be rendered into a form on the Angular side. Also a "default" profile plugint that a site grabber from this provider should run on.
