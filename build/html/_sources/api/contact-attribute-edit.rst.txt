Contact Attribute Edit Endpoint
==============

+-------------------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                           | Required Values   | HTTP Methods    |
+===============================================================================+===================+=================+
| https://app.tingting.io/api/v1/campaign/<contact_id>/attributes/              | Contact ID        | PATCH           |
+-------------------------------------------------------------------------------+-------------------+-----------------+

Note that the <contact_id> in the URL should be replaced with the ID of the contact you want to edit the attributes of.

Sample Input:

.. code-block:: json

    {
        "age" : "22",
        "name" : "Ram",
        "salary" : "200000"
    }

The details after the updating is successfully completed is shown

Sample Output:

.. code-block:: json

    {
        "age": "22",
        "name": "Ram",
        "salary": "200000"
    }