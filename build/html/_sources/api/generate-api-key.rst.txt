Generate API Token Endpoint
=============================

+----------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                  | Required Values   | HTTP Methods    |
+======================================================================+===================+=================+
| https://api.tingting.io/api/v1/auths/generate-api-keys/    |                   | POST            |
+----------------------------------------------------------------------+-------------------+-----------------+

This endpoint is used to generate a new API token for the authenticated user. When a new token is generated, any previous keys are automatically soft-deleted, ensuring only one valid pair exists at a time.

You must include a valid Bearer Token in the request header to access other endpoint.

Header Example:

.. code-block:: http

    Authorization: Bearer <your_access_token>

Sample Request:
(No body is required)

Sample Output:

.. code-block:: json

    {
        "token": 7acbdcd5619e4b9eaaad8e41dabb7032298e1acdf8fbc99bfae70561b51cdee7,
        "message": "New API token generated successfully"
    }
