
Predictive Services Query Client (psquery)
======================================

This package allows you to query Turi Predictive Services.

Refer to
https://turi.com/products/predictive-services/docs/userguide/connecting.html#psquery
for detailed information regarding how to use this client.

This package only includes the config.py and query_client.py from the full
Predictive Services client psclient.


Connecting
----------

In order to connect, you need to know the query endpoint URL and your key. An
API key or an admin key is sufficient to query the Predictive Services. An API
key may have limitations on which endpoints it can query. Consult with your
system administrator to obtain the appropriate key.

The :func:`psquery.connect` function is used to connect to the service.

    >>> import psquery
    >>> conn = psquery.connect(query_endpoint_URL, key_id)


Please consult the documentation for details on alternative methods of
connecting.


Querying
--------

Once you have connected, you can query by specifying the endpoint you want to
query and the parameters. Keep in mind that your key must have sufficient
privileges to access the endpoint. Admin keys can access all endpoints, but
API keys must be specifically allowed by endpoint name.

    >>> response = onn.query('add', 1, 2)
    >>> response
    {u'node': u'...', u'uuid': u'...', u'version': 1, u'from_cache': False,
    u'model': u'add', u'response': 3}

Feedback
--------

If the endpoint allows it, you can specify feedback:

    >>> conn.feedback(response['uuid'], success=True)

