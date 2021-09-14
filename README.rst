==================
Simple API Enpoint
==================

Version: 0.0.2
Author: Chris Marrison
Email: chris@infoblox.com

Description
-----------

This script is designed to provide a simple way to demonstrate
the or debug the Infoblox NIOS outbound API with a simple 'receiver' for 
POSTs and a simple GET to display the received data records.


Prerequisites
-------------

Python 3.6 or above with flask


Installing Python
~~~~~~~~~~~~~~~~~

You can install the latest version of Python 3.x by downloading the appropriate
installer for your system from `python.org <https://python.org>`_.

.. note::

  If you are running MacOS Catalina (or later) Python 3 comes pre-installed.
  Previous versions only come with Python 2.x by default and you will therefore
  need to install Python 3 as above or via Homebrew, Ports, etc.

  By default the python command points to Python 2.x, you can check this using 
  the command::

    $ python -V

  To specifically run Python 3, use the command::

    $ python3


.. important::

  Mac users will need the xcode command line utilities installed to use pip3,
  etc. If you need to install these use the command::

    $ xcode-select --install

.. note::

  If you are installing Python on Windows, be sure to check the box to have 
  Python added to your PATH if the installer offers such an option 
  (it's normally off by default).


Modules
~~~~~~~

Non-standard modules:

    - flask

Install using::

    pip3 install flask --user

    import flask
    import json


Usage
-----

The script uses the build in flask development server for simplicity running 
on the default port 5000 and binding to all IP addresses (including localhost).

To run the script::

    % python3 simple_api_endpoint.py


The script will start the server and display the URL for the endpoint.

This can then be tested with curl or postman.

Two simple HTTP methods are provided using the root path '/': GET and POST.

    - POST - When calling '/' using POST a JSON body is expected and stored in
    a list.

    - GET - When calling '/' using GET this will respond with the list of JSON
    records.


NIOS Outbound Templates
~~~~~~~~~~~~~~~~~~~~~~~

Several example Outbound API templates are provided for simple demonstrations.

You will need to configure:

    - Endpoint
    - notifications
    - Template

Create the enpoint with the URL provided when you ran the script.

.. note::

    The Endpoint should be called SIMPLE_API_DEMO to match the template.

Upload the appropriate template you wish you use.

Configure the notifications, for example, with the network templates you can
create notifications on "Object Change Network IPv4" and add a rule for
*network-view equals default* which will trigger based on network changes to
the default network view.


License
-------

This project is licensed under the 2-Clause BSD License

- please see LICENSE file for details.

Aknowledgements
---------------

Thanks to the Ross Gibson for testing and Sif Baksh for additional Outbound 
API templates and assistence with these.
