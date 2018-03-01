.. _getting-started:

Getting Started
===============

Official openstack api documentation: https://developer.openstack.org/api-guide/quick-start/


Create file ``api-rc``:

.. literalinclude:: api-rc
   :language: bash

.. code-block:: bash

   source api-rc


.. code-block:: bash

   curl -v -s -X POST $OS_AUTH_URL/auth/tokens?nocatalog   -H "Content-Type: application/json"   -d '{ "auth": { "identity": { "methods": ["password"],"password": {"user": {"domain": {"name": "'"$OS_USER_DOMAIN_NAME"'"},"name": "'"$OS_USERNAME"'", "password": "'"$OS_PASSWORD"'"} } }, "scope": { "project": { "domain": { "name": "'"$OS_PROJECT_DOMAIN_NAME"'" }, "name":  "'"$OS_PROJECT_NAME"'" } } }}' | python -m json.tool
