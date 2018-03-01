## Index

.. code-block:: yaml

  all:
    hosts:
      mail.example.com
    children:
      webservers:
        hosts:
          foo.example.com:
          bar.example.com:
      dbservers:
        hosts:
          one.example.com:
          two.example.com:
          three.example.com:


.. note:: Values passed in the INI format using the ``key=value`` syntax are not interpreted as Python literal structure
          (strings, numbers, tuples, lists, dicts, booleans, None), but as a string. For example ``var=FALSE`` would create a string equal to 'FALSE'.
          Do not rely on types set during definition, always make sure you specify type with a filter when needed when consuming the variable.

=====  =====  =======
A      B      A and B
=====  =====  =======
False  False  False
True   False  False
False  True   False
True   True   True
=====  =====  =======
