Dashboard Endpoint
=================

+----------------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                        | Required Values   | HTTP Methods    |
+============================================================================+===================+=================+
| https://app.tingting.io/api/v1/dashboard/                                  |                   | GET             |
+----------------------------------------------------------------------------+-------------------+-----------------+

**Authentication:** IsCompanyUser (authenticated company user)

**Query parameters (optional):**

+----------+----------------------------------------------------------+
| Param    | Description                                              |
+==========+==========================================================+
| days     | Number of days to include in the stats (default: 30)      |
+----------+----------------------------------------------------------+

Use this endpoint to fetch dashboard statistics for the current company user. All values are computed over the last ``days`` days.

Response body
-------------

The response is a JSON object with the following keys:

+---------------------------+--------------------------------------------------------------------------------------------------+
| Key                       | Meaning                                                                                          |
+===========================+==================================================================================================+
| total_credits_purchased   | Total credits bought                                                                             |
+---------------------------+--------------------------------------------------------------------------------------------------+
| credits_used              | Credits consumed                                                                                 |
+---------------------------+--------------------------------------------------------------------------------------------------+
| remaining_credits         | Credits left                                                                                     |
+---------------------------+--------------------------------------------------------------------------------------------------+
| campaigns                 | Campaign-level stats (from get_campaign_stats)                                                   |
+---------------------------+--------------------------------------------------------------------------------------------------+
| outbound_calls            | Outbound call counts (from campaign action details)                                               |
+---------------------------+--------------------------------------------------------------------------------------------------+
| outbound_sms              | Outbound SMS counts                                                                              |
+---------------------------+--------------------------------------------------------------------------------------------------+
| total_call_duration       | Total call duration                                                                              |
+---------------------------+--------------------------------------------------------------------------------------------------+
| total_owned_numbers       | Count of owned phone numbers                                                                     |
+---------------------------+--------------------------------------------------------------------------------------------------+
| total_playback             | Playback-related stats (from campaign action details)                                             |
+---------------------------+--------------------------------------------------------------------------------------------------+
| credit_spent              | Average credit spent (from avg_credit_spent)                                                      |
+---------------------------+--------------------------------------------------------------------------------------------------+
| top_performing_campaign   | Best campaign by completion % (from top_performing_campaign)                                      |
+---------------------------+--------------------------------------------------------------------------------------------------+
| playback_distribution     | Playback distribution                                                                            |
+---------------------------+--------------------------------------------------------------------------------------------------+
| campaign_type_ratio       | Breakdown by campaign type (from get_campaign_type)                                                |
+---------------------------+--------------------------------------------------------------------------------------------------+
| call_outcomes             | Call outcome stats (from get_call_outcomes)                                                       |
+---------------------------+--------------------------------------------------------------------------------------------------+
| credit_usage_overtime     | Credit usage over time                                                                            |
+---------------------------+--------------------------------------------------------------------------------------------------+

Sample request
--------------

::

    GET /api/v1/dashboard/?days=30
    Authorization: Bearer <access_token>

Sample output
-------------

.. code-block:: json

    {
        "total_credits_purchased": 1000,
        "credits_used": 450,
        "remaining_credits": 550,
        "campaigns": {},
        "outbound_calls": 1200,
        "outbound_sms": 300,
        "total_call_duration": "05:30:00",
        "total_owned_numbers": 5,
        "total_playback": {},
        "credit_spent": 0.375,
        "top_performing_campaign": {},
        "playback_distribution": {},
        "campaign_type_ratio": {},
        "call_outcomes": {},
        "credit_usage_overtime": []
    }

The structure and types of nested objects (e.g. ``campaigns``, ``playback_distribution``, ``call_outcomes``) match the underlying sources (get_campaign_stats, get_campaign_type, get_call_outcomes, etc.).
