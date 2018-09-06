########
PyPexels
########

I have updated the code for python 3.5+.

An open source Python wrapper for the `Pexels REST API <https://www.pexels.com/api/>`_.

The source code in Python 2.7 available on GitHub at `https://github.com/salvoventura/pypexels <https://github.com/salvoventura/pypexels>`_. 

The source code in Python 3.5+ available on Github at `https://github.com/AkankshaMalhotra/pypexels/ <https://github.com/AkankshaMalhotra/pypexels/>`_.


.. note::  When using this library you still need to abide to Pexels Guidelines, which are explained on `Pexels API page <https://www.pexels.com/api/>`_


############
Installation
############


############
Dependencies
############
This library depends on `Requests <http://docs.python-requests.org>`_ to make - well - requests to the Pexels API.
This additional package should be automatically installed at installation time, or you can simply install it by:
::

    $ pip install requests

########
Examples
########
This example shows how the interaction with the paging functionality of the Pexels API is greatly abstracted and
simplified. The code below will iterate through all popular images, and print attributes for each photo in there.

.. code-block:: python

    from pypexels import PyPexels
    api_key = 'YOUR_API_KEY'

    # instantiate PyPexels object
    py_pexels = PyPexels(api_key=api_key)

    popular_photos = py_pexels.popular(per_page=30)
    while popular_photos.has_next:
        for photo in popular_photos.entries:
            print(photo.id, photo.photographer, photo.url)
        # no need to specify per_page: will take from original object
        popular_photos = popular_photos.get_next_page()

#############
Documentation
#############
Documentation is published on `ReadTheDocs <http://pypexels.readthedocs.io/>`_.


#######
License
#######
PyPexels is released under the `MIT License <http://www.opensource.org/licenses/MIT>`_.
