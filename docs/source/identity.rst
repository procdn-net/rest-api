identity endpoint
=================

POST /api/v1/tokens
-------------------

Create JWT. User authorization.

*Example request*

.. code-block:: console

   curl -X POST https://api.procdn.net/api/v1/tokens \
   -H 'Content-Type: application/json' \
   -d '{
      "email": "{{email}}",
      "password": "{{password}}"
   }'


*Response*

.. code-block:: json

   {
      "payload": {
         "token": "{JWT}"
      },
      "status": {
         "code": "CDN_0001",
         "message": "Created.",
         "severity": "info"
      }
   }


*JWT Content*

.. code-block:: json
   {
      "token": "6e1c58be-4da0-4072-81e7-7e412d3640b6",
      "email": "vanzhiganov@ya.ru",
      "user_id": "6cc50407-92a3-4189-89e5-53b3cdab53c2",
      "attrs": {
         "phone": "+79832756171",
         "mobile": "+79832756171"
      }
   }

GET /api/v1/user/details
------------------------

Get Account Details.

*Request*

.. code-block:: console
   curl https://api.procdn.net/api/v1/user/details

*Response*

.. code-block:: json
   {
      "payload": {
         "address": "",
         "city": "",
         "country": "",
         "fname": "test1",
         "lname": "",
         "state": "",
         "zipcode": "0"
      },
      "status": {
         "code": "CDN_0000",
         "message": "Success.",
         "severity": "info"
      }
   }

GET /api/v1/user/attributes
---------------------------

Get Account Attributes.

*Request*

.. code-block:: console

   curl "https://api.procdn.net/api/v1/user/attributes" \
      -H "Authorization: ${JWT}"

*Response*

.. code-block:: json
   {
      "payload": [
            {
            "name": "phone",
            "type": "string",
            "value": "+79832756171"
         },
         {
            "name": "mobile",
            "type": "string",
            "value": "+79832756171"
         }
      ],
      "status": {
         "code": "CDN_0000",
         "message": "Success.",
         "severity": "info"
      }
   }

POST /api/v1/user/attributes
----------------------------

Create a new Account Attribute.

*Request*

.. code-block:: console
   curl -X POST "https://api.procdn.net/api/v1/user/attributes" \
      -H "Authorization: ${JWT}" \
      -H "Content-Type: application/json" \
      -d '{
         "name": "mobile",
         "type": "string",
         "value": "+79832756171"
      }'

*Response*

.. code-block:: json
   {
   }

DELETE /api/v1/user/attributes/{attribute}
------------------------------------------

Delete Account Attribute.

*Request*

.. code-block:: console
   curl -X DELETE "https://api.procdn.net/api/v1/user/attributes/mobile" \
      -H "Authorization: ${JWT}"


*Response*


.. code-block:: json
   {
   }

GET /api/v1/user/attributes/{attribute}
-------------------------------------------

Get Account Attribute.

*Request*

.. code-block:: console

   curl "https://api.procdn.net/api/v1/user/attributes/mobile" \
      -H "Authorization: ${JWT}"

*Response*

.. code-block:: json

   {
   }

GET /api/v1/user/secret
-----------------------

Get Account Secret.

*Request*

.. code-block:: console

   curl "https://api.procdn.net/api/v1/user/secret" \
      -H "Authorization: ${JWT}"

*Response*

.. code-block:: json

   {
   }
