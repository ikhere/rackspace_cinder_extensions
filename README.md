# Rackspace Cinder Extensions

Extensions to [OpenStack](http://www.openstack.org/) [Cinder](https://github.com/openstack/cinder),
created by Rackers to enhance operations and the customer experience.

### Installation

The included `setup.py` can be used to build `.deb` files for Debian or Ubuntu.
First you'll need to install some prerequisite packages:

    apt-get install python-stdeb fakeroot python-all

To build for a specific release create a `stdeb.cfg` file and add the following,
replacing `trusty` with your release codename:

    [DEFAULT]
    Suite: trusty

Now build the `.deb` file:

    python setup.py --command-packages=stdeb.command bdist_deb

### Load all extensions in the Rackspace extension package

Add this line to `cinder.conf`:

    osapi_volume_extension = rackspace_cinder_extensions.api.contrib.standard_extensions

### Load extensions by name:

Add these lines to `cinder.conf`:

    osapi_volume_extension = rackspace_cinder_extensions.api.contrib.select_extensions
    rsapi_volume_ext_list = Volume_list_admin_context,Snapshot_progress
