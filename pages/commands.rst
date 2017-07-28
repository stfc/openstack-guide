Openstack Client commands
==============================

If you 'openstack' into the command line, your commands will automatically be recognised as openstack commands so you do not have to preface them with 'openstack' until you exit with ^c 

Instances (Servers)
---------------------

To view a list of running instances, use the command::

  openstack server list

You can also create an instance with the command::

  openstack server create <name>

You will need to specify a key pair, image and flavour for this instance using --key-name, --image and --flavor. There are also other parameters, tht you can find with the command list linked at the bottom of the page.

Images
----------

View available images with::

  openstack image list

You can refine the list with various parameters.

Key pairs 
--------------


Create a key pair using::

  openstack keypair create

You have to specify a name, and optionally you can add filenames for the public or private keys. If a public key is not specified, then only a private key will be created.


You can list the key pairs available with::

   openstack keypair list

And delete with::

  openstack keypair delete

Security Groups
-----------------

Create a security group using::
  
  openstack security group create <name>

You can add a description with --description.

List with::

  openstack security group list

And delete with::

  openstack security group delete

Add a security group rule with::

  openstack security group rule create <group>

See the perameters here_.

.. _here: https://docs.openstack.org/python-openstackclient/latest/cli/command-objects/security-group-rule.html

Volumes
-----------

Create a volume with::
  
  openstack volume create <name>

See parameters_.

.. _parameters: https://docs.openstack.org/python-openstackclient/latest/cli/command-objects/volume.html

You can also set the properties of volumes once they have been created, with::
  
  openstack volume set <volume>

`full list of commands for openstack client`__.

__ commands_

.. _commands: https://docs.openstack.org/python-openstackclient/latest/cli/command-list.html#command-list


