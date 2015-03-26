# StartledPhoenix/openshift-diy-cachet

This is a DIY repository for running [Cachet](https://cachethq.io/) on OpenShift, based on [boekkooi/openshift-diy-nginx-php](https://github.com/boekkooi/openshift-diy-nginx-php)

More information about openshift: https://openshift.redhat.com/

## Installation

To install, follow these steps:

1. Create a new Openshift "Do-It-Yourself" application
2. Add the MySQL Cartridge to the application
3. Clone this repository (You might fork it if you want)
  
  ```
  git clone https://github.com/StartledPhoenix/openshift-diy-cachet.git
  ```
4. Update the submodules

  ```
  git submodule init
  git submodule update
  ```
5. Go to your application page on OpenShift, and copy the text under 'Source Code', and run the below (replace ssh://.... with your own text)

  ```
  git remote add openshift ssh://....
  ```
6. Run `git push --force "openshift" master:master`
7. Wait for build to finish (This may take at least an hour). See below for what to do when the build times out.
8. Open http://appname-namespace.rhcloud.com/ to verify

#### Openshift disconnects on build
This seems to be a problem within openshift (see https://www.openshift.com/forums/openshift/openshift-build-timeout).

To resume the build, first make an arbitary change to your local repo (e.g. add some text to README.md), commit that change and then do another `git push --force "openshift" master:master`.

## Additional
For automatic redirection to HTTPS, uncomment the block at line 112 in .openshift/tmpl/nginx.conf.tmpl

## Thanks

Thanks to the following people:

* [@boekkooi](https://github.com/boekkooi) for developing the initial nginx/php DIY, which this repository is based on.
* [@sgoettschkes](https://github.com/Sgoettschkes)
* [@drejohnson](https://github.com/drejohnson)
* [@openshift](https://github.com/openshift/)
