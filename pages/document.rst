Modify this directory
=====================

This section shows you how to modify, create and remove pages from this directory to expand its use. This directory was created with Sphinx, often used to document Python code. Hopefully you have downloaded these files from the git repository and set up sphinx in order to create the html for the pages.

Add pages
-----------

To add a page, simply create a new .rst file in the openstack-guide/pages/ directory. When the 'make html' command is run, the Sphinx program will automatically create a .html file based on the .rst file. These files are stored in the _build/html directory and will be named the same as the .rst is named if you want to directly edit the html (but this will reset every time the 'make html' command is run again).

The name of the page will also have to be included in a toctree in either the main index document: index.rst, or another document to create a sub-page. The document's name needs to be inputted (without .rst).

Modify an existing page
----------------------------

All the .rst files can easily be modified using any Linux text editor. To apply the changes to the pages, make sure to run the 'make html' command.

Add images to pages
-----------------------

Use the command '..image: <image file address>' to add an image to the page. The images are higher quality if they are sourced from upload rather than downloading them into the VM (using 'curl')  and using them, but there is an image file to organise images if needed. I used imgbb to upload screenshots, as this was the highest quality I found.

