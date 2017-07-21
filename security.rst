Access & Security
=================

This is where you manage what can ping and connect to your virtual machine. It will be necessary to set up security groups and a key pair to be able to access your virtual machine.

.. image:: https://preview.ibb.co/jDtc75/security.png

Add a security rule
---------------------

- Click 'manage rules' on the security group you want to edit (likely this will be the default security group).

.. image:: https://preview.ibb.co/g2vFS5/rules.png

- From here you can delete or create rules.

- To create a new rule, click the 'add rule' button and a dialouge box will appear. To set up your virtual machine you will need two new rules:

.. image:: https://preview.ibb.co/msy275/addssh.png

- For allowing requests from IP addreses, create a SSH rule (at the bottom of the dropdown menu), choose the remote CIDR and 0.0.0.0/0 for any ip addresses

.. image:: https://preview.ibb.co/nBfFS5/addicmp.png

- To allow all ICMP packets, also create an 'all ICMP' rule, with an ingress direction, the remote CDIR and all IP addresses again


Add a key pair
---------------

- Click the 'key pairs' tab, on the top left of the page and click the 'create key pair' button.

.. image:: https://preview.ibb.co/io2yEk/keypair.png

- A dialouge box will pop up that asks you for a name for the key pair.Enter a name and the key will be downloaded. You can then save the key where you want; you will need it to access any instance you create.

.. image:: https://preview.ibb.co/dHCyEk/newkey.png


