Getting Started
===============

This Python module makes it easy to interact with the Data North API.  It can be used in your scripts to quickly pull or query the data you need for your application.

Installation
------------

Start by installing ``datanorth``.  The easiest with is with **pip**::

    pip install datanorth --upgrade


Configuring the Project
-----------------------

The client should only be instantiated once for your application.  The instance can then be used for querying and pulling data::

    from datanorth import Project
    client = Project('https://helloworld@datanorth.io/<project>')

Example Usage
-------------

Once you have an authenticated session, you can query and download the data in a few different ways::

    from datanorth import Project
    project = Project('https://helloworld@datanorth.io/<project>')

    # List the available endpoints
    print(project.endpoints)

    # Get an iterator for all the data and iterate over everything
    scan = project.scan()
    for s in scan:
        print(s)

    # Get an iterator only for data matching a primary key
    scan = project.scan(key='year')
    for s in scan:
        print(s)

