Openstack Client commands
==============================

If you type in openstack, your commands will automatically be recognised as openstack commands until you exit with ^c 


Images
----------

View available images with::

  openstack image list

you can refine the list with various parameters

Key pairs 
--------------


create a key pair using::

  openstack keypair create

you have to specify a name, and optionally you can add filenames for the public or private keys. If a public key is not specified, then only a private key will be created.


you can list the key pairs available with::

   openstack keypair list

and delete with::

  openstack keypair delete

Security Groups
-----------------

create a security group using::
  
  openstack security group create <name>

you can add a description with --description.

list with::

  openstack security group list

and delete with::

  openstack security group delete

add a security group rule with::

  openstack security group rule create <group>

see the perameters here_.

.. _here: https://docs.openstack.org/python-openstackclient/latest/cli/command-objects/security-group-rule.html

Volumes
-----------

create a volume with::
  
  openstack volume create <name>

see parameters_.

.. _parameters: https://docs.openstack.org/python-openstackclient/latest/cli/command-objects/volume.html

you can also set the properties of volumes once they have een created, with::
  
  openstack volume set <volume>

`full list of commands for openstack client`__.

__ commands_

.. _commands: https://docs.openstack.org/python-openstackclient/latest/cli/command-list.html#command-list


