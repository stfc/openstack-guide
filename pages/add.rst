Add pages 
==========

To add a page, simply create a new .rst file in the openstack-guide directory. When the 'make html' command is run, the Sphinx program will automatically create a .html file based on the .rst file. These files are stored in the _build/html directory and will be named the same as the .rst is named if you want to directly edit the html.

The name of the page will also have to be included in a toctree in either the main index document: index.rst, or another document to create a sub-page. The document's name needs to be inputted (without .rst)

 
