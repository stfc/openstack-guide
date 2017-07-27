Cloud-Init
==============

Clout init is a set of scripts that are executed when booting up an instance or stack. Most commercial images have it pre-installed on their images, but it also allows the user to customise how an instance boots by submitting user-data when creating an instance. This allows the user to provide the instance with users, files and scripts that should be installed when the instance boots.

This user data can be submitted as a cloud config file using YAML syntax to present information for the instance when it is booting or through a shell script. You can supply user data for an instance or stack either throught the Openstack dashboard, or by suppling a user data   file when booting up through the Openstack or heat command line client.

Through the dashboard
-----------------------

When you are launching an instance, the configuration tab allows you to paste a script in the box that contains user data, or you can upload a file from your computer.

.. image:: https://preview.ibb.co/d8Jzc5/configuration.png

Through the command line 
-----------------------------

You can specify user data when booting a stack using the command::

   heat stack create <stack_name> --user-data <file>

Cloud Config Files
----------------------

All cloud config files must have::

  #cloud-config

in the first line if they are a cloud config file, or::

 #!

if they are a shell-script.

For cloud config files, the first step using the cloud config is to define users that you will have in your cloud::
  
   users:
     - name: example
       groups: sudo
       shell: /bin/bash
       sudo: ['ALL=(ALL) NOPASSWD:ALL']
       ssh-authorized-keys:
         - ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDf0q4PyG0doiBQYV7OlOxbRjle026hJPBWDAaaaaxcdxd+eKHWuVXIpAiQlSElEBqQn0pOqNJZ3IBCvSLnrdZTUph4czNC4885AArS9NkyM7lK27Oo8RV8+NI5xPB/QT3Um2Zi7GRkIwIgNPN5uqUtXvjgAaaaaaaffcdc+i1CS0Ku4ld8vndXvr504jV9BMQoZrXEST3YlriOb8Wf7hYqphVMpF3b+8df96Pxsj0+iZqayS9wFcL8ITPApHi0yVwS8TjxEtI3FDpCbf7Y/DmTGOv49+AWBkFhS2ZwwGTX65L61PDlTSAzL+rPFmHaQBHnsli8U9N6E4XHDEOjbSMRX

This snippet creates a user called example, who has access to sudo commands, uses the bash shell script, and has the listed SSH key added into their authorised keys. The full list of parameters for a user can be seen `here <https://www.digitalocean.com/community/tutorials/an-introduction-to-cloud-config-scripting>`_

groups can also be created to group users

You can also create and write to a file in the new server using write_files::

  write_files:
    - path: /test.txt
      content: |
        Here is a line.
        Another line is here.

All text that has no commands in should be prefaced by a '|' symbol.

You can also run commands when booting using bootcmd and runcmd in your config file.

For a more extensive list of commands, read the `cloud-init readthedocs <http://cloudinit.readthedocs.io/en/latest/topics/examples.html>`_.

