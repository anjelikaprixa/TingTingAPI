Get API Token Endpoint
=============================

+--------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                | Required Values   | HTTP Methods    |
+====================================================================+===================+=================+
| https://api.tingting.io/api/v1/auths/get-api-keys/       |                   | GET             |
+--------------------------------------------------------------------+-------------------+-----------------+

This endpoint returns the API token associated with the currently authenticated user. This token can be used as an alternative to JWT login for authenticating API requests.

Sample Output (when API token exists):

.. code-block:: json

    {
        "token": "39106a38ac483eb4625308fe98411588",
        "last_used": "2025-02-20T14:30:00.000Z",
        "created_at": "2025-03-14T14:30:00.000Z",
    }

Sample Output (when API token is not found):

.. code-block:: json

    {
        "message": "No API token found. Please generate one first."
    }

**How to Use API Token**

Once you retrieve the API token, you can authenticate without logging in again by passing them as Bearer Token for other endpoints.

You must include a valid Bearer Token in the request header to access other endpoint.

Header Example:

.. code-block:: http

    Authorization: Bearer <your_access_token>