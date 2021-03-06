Quickstart
==========

This page gives an introduction to Muffin. It assumes you already have the
library installed, how it described in :ref:`installation` section.

An Example Application
----------------------

A minimal Muffin application looks something like this:

.. code-block:: python

    import muffin

    app = muffin.Application('example')

    @app.register('/', '/hello/{name}')
    def hello(request):
        name = request.match_info.get('name', 'anonymous')
        return 'Hello %s!' % name

What did that code do?

1. First we imported the :class:`~muffin.Application` class.  An instance of
   this class will be our application.
2. Next we create an instance of this class. The first argument is the name of
   the application.
3. We then use the :meth:`~muffin.Application.route` decorator to tell Muffin
   what URLs should trigger our handler function.
4. The function returns the message we want to display in the user's browser.
