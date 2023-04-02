Wagtail Colour Picker
=====================

A colour picker for Wagtail's DraftJS editor.

Preamble
--------

I basically poached the starting point for this from https://github.com/Vadim-Karpenko/wagtailcolourpicker.git@master but there were a few problems
with it that prevented it from working with the latest version of Wagtail (which at the time of writing was 4.2).  I think I have got it working now 
but really it does need some decent community testing.  The rest of the documentation below is basically from his GitHub repository.


Installation
------------

<code bash>

   ~~pip install git+https://github.com/Vadim-Karpenko/wagtailcolourpicker.git@master~~
   gh repo clone kiwiheretic/wagtailcolourpicker
</code>

Setup
-----

Add to installed app:

<code python>

   INSTALLED_APPS = [
      ...
      'wagtailcolourpicker',
      ...
   ]
</code>

Settings
--------

<code python>

   # picker icon
   WAGTAILCOLOURPICKER_ICON = ['...']
   # Add your colours
   WAGTAILCOLOURPICKER_COLOURS = {
      'black': '#000000',
      'white': '#ffffff'
   }
</code>

Models
------
Add into your models.py

<code python>

    # Add all colors from 'wagtailcolourpicker'
    # list names into your RichTextField(features=[get_list_features_name()]
    body.features += get_list_colour_features_name()
</code>

Documentation
-------------

Can be found on `readthedocs <http://wagtailcolourpicker.readthedocs.io/>`_.

Screenshots
-----------

.. figure::  http://wagtailcolourpicker.readthedocs.io/en/latest/_images/screen_1.png
   :width: 728 px

Picker

.. figure:: http://wagtailcolourpicker.readthedocs.io/en/latest/_images/screen_2.png
   :width: 728 px

Selected Text

Example site with docker
------------------------

Clone the repo

.. code:: bash

    $ git clone https://github.com/AccentDesign/wagtailcolourpicker.git

Run the docker container

.. code:: bash

    $ cd wagtailcolourpicker
    $ docker-compose up

Create yourself a superuser

.. code:: bash

    $ docker-compose exec app bash
    $ python manage.py createsuperuser

Go to http://127.0.0.1:8000/cms and add a new basic page
