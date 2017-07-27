Using Heat
=================

Heat is the openstack cloud orchestration service that allows users to create templates, thet can then be read as code and used to automatically create cloud resources. The templates also can be used to show which things link to each other, eg. instances and security groups.

Setup
-------

To install a heat client on your vm, use::

   sudo yum install python-heatclient

(or use pip) 

to test if it is working, type heat into the command line and a list of options should appear.

HOT
------------

Heat orchestration templates are .yaml files that are used in heat to define parameters of cloud resources and scripts that should be run on setup of the cloud resources, and can output certain attributes of the resources you are creating. You can also nestle the templates inside of each other which allows the user to create useful, reusable templates.

A very simple template to just launch an instance would look something like this::

  heat_template_version: 2015-04-30

  description: Simple template to deploy a single compute instance

  resources:
    my_instance:
      type: OS::Nova::Server
      properties:
        key_name: my_key
        image: ubuntu-trusty-x86_64
        flavor: m1.small

A template must begin with the HOT template version. `Full list of versions <https://docs.openstack.org/heat/latest/template_guide/hot_spec.html#heat-template-version>`_.

A template usually has 4 main sections: a description (though this is not necessary); parameters, which declares the inputs to the template; resources, which states resources that are being created; and outputs, which takes attributes from resources and outputs them. This template only has resources because it is not taking any external parameters or outputting anything, but this makes it a bad template as it cannot adapt.

This following template allows parameters to be inputted by the person who runs the command::

  heat_template_version: 2015-04-30

  description: Simple template to deploy a single compute instance

  parameters:
    key_name:
      type: string
      label: Key Name
      description: Name of key-pair to be used for compute instance
      default: heat_key
    image_id:
      type: string
      label: Image ID
      description: Image to be used for compute instance
      default: ScientificLinux-7-NoGui
    flavor:
      type: string
      label: Instance Type
      description: Type of instance (flavor) to be used
      default: m1.small

  resources:
    my_instance:
      type: OS::Nova::Server
      properties:
        key_name: { get_param: key_name }
        image: { get_param: image_id }
        flavor: { get_param: flavor }

This is more useful because the parameters can be chosen. All the parameters also have defaults, which is needed because if someone ran the template without inputting any parameters, the instance could still boot.

Heat templates are most useful as you are able to create many resources in one template and link them together.

For a more detailed introduction and tutorial, look at the `OpenStack Orchestration In Depth Guide <https://developer.rackspace.com/blog/openstack-orchestration-in-depth-part-1-introduction-to-heat/>`_

