List Send OTP Endpoint
==============

+---------------------------------------------------------------------+-------------------+---------------+
| URL                                                                 | Required Values   | HTTP Methods  |
+=====================================================================+===================+===============+
| https://app.tingting.io/api/v1/auths/list/send-otps/                |                   |     GET       |
+---------------------------------------------------------------------+-------------------+---------------+

This endpoint lists OTPs sent by the authenticated user.

Sample Output:

.. code-block:: json

    {
    "count": 2,
    "total_pages": 1,
    "next": null,
    "previous": null,
    "results": {
        "status": 200,
        "success": true,
        "errors": [],
        "data": [
            {
                "id": 12,
                "phone_number": "9861489014",
                "message": "Hi,  your otp is 12345",
                "otp": "12345",
                "otp_options": "personnel",
                "sms_send_options": "text",
                "created_at": "2025-10-29T13:33:55.512191+05:45"
            },
            {
                "id": 11,
                "phone_number": "9861489014",
                "message": "Hi,  your otp is 12345",
                "otp": "12345",
                "otp_options": "personnel",
                "sms_send_options": "text",
                "created_at": "2025-10-29T13:33:47.088108+05:45"
            }
        ]
    }
}