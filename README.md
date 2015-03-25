# StartledPhoenix/openshift-diy-cachet

This is a DIY repository for running [Cachet](https://cachethq.io/) on OpenShift, based on boekkooi/openshift-diy-nginx-php

More information about openshift: https://openshift.redhat.com/

## Installation

To install, follow these steps:

1. Create a new Openshift "Do-It-Yourself" application
2. Clone this repository
3. Add a new remote "openshift" (You can find the URL to your git repository
   on the Openshift application page)
4. Run `git push --force "openshift" master:master`
5. SSH into your gear
7. Wait for build to finish (This may take at least an hour)
8. Open http://appname-namespace.rhcloud.com/ to verify

#### Openshift disconnects on build
This seems to be a problem within openshift (see https://www.openshift.com/forums/openshift/openshift-build-timeout).

To resume the build, first make an arbitary change to your local repo (e.g. add some text to README.md), commit that change and then do another `git push --force "openshift" master:master`.

## Thanks

Thanks to the following people:

* [@boekkooi](https://github.com/boekkooi) for developing the initial nginx/php DIY, which this repository is based on.
* [@sgoettschkes](https://github.com/Sgoettschkes)
* [@drejohnson](https://github.com/drejohnson)
* [@openshift](https://github.com/openshift/)
