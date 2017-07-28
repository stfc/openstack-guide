Openstack Client Setup
========================


To install Openstack Client on your virtual machine, you can run the command::

  pip install python-openstackclient

Or, alternatively::

  yum install python-openstackclient

Openstack Client may already be installed on your machine if you are using the Scientific Linux 7 image.

Startup
------------------

To link Openstack Client to your dashboard you will need to authenticate it using keystone:

- go to API Access in the access and security tab and download Openstack RC File V3,

- Copy the contents of the file and paste it into a file of the same name in your VM,

- Source that file and enter your Openstack dashboard password.

- You will have to source the file every new session because your password is not stored.


