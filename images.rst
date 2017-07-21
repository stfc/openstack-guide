Images
=======

Images are the operating systems that you use to launch your virtual machines. There are probably images already available to you in the images tab, or you can download one that is premade.
You can find links to downloads here_.

.. _here: https://docs.openstack.org/image-guide/obtain-images.html#red-hat-enterprise-linux


You can manage your available images in the images tab:

.. image:: https://preview.ibb.co/kXeAc5/compare.png

Create an Image
-----------------------

If you wish to upload an image into Openstack that you have downloaded:

.. image:: https://preview.ibb.co/dbuMjk/createimage.png

- Click "Create Image" in the top right of the images tab and a box like below will pop up.

.. image:: https://preview.ibb.co/d6yWjk/newimage.png
    :width: 300pt

- Name and describe the image you are creating.

- Choose either to source your image from a URL (pick 'image location') or from a file you have downloaded (pick 'image file).

- Specify the architecture such as whether the image is 32 or 64-bit.

- Leave the minimum disk and RAM blank.

- Making an image protected means that only people with permissions can delete the image.

 
