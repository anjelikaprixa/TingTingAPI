Download Report Endpoint
========================

Campaign report
---------------

+----------------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                        | Required Values   | HTTP Methods    |
+============================================================================+===================+=================+
| https://app.tingting.io/api/v1/download/report/<campaign_id>/             | Campaign ID       | GET             |
+----------------------------------------------------------------------------+-------------------+-----------------+

Replace ``<campaign_id>`` with the campaign ID you want to download the report for.

This endpoint downloads campaign report in CSV format.

Survey report (separate endpoint)
---------------------------------

+--------------------------------------------------------------------------------+-------------------+-----------------+
| URL                                                                            | Required Values   | HTTP Methods    |
+================================================================================+===================+=================+
| https://app.tingting.io/api/v1/download/survey/<survey_id>/report/            | Survey ID         | GET             |
+--------------------------------------------------------------------------------+-------------------+-----------------+

Replace ``<survey_id>`` with the survey ID you want to download the survey report for.

Query parameters (optional)
^^^^^^^^^^^^^^^^^^^^^^^^^^^

+-----------+---------------------------------------------------------------+
| Param     | Description                                                   |
+===========+===============================================================+
| format    | Use ``json`` to return JSON response.                        |
|           | Default response is CSV when format is not provided.         |
+-----------+---------------------------------------------------------------+

Example:

::

    GET /api/v1/download/survey/16294/report/?format=json