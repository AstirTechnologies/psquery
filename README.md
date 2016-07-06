# Predictive Services Python Client Library

## Installation

     pip install psquery

## Usage

    import psquery

    ps = psquery.Service(
    	base_url='...',
	api_keyxcvc'...')

    ps.query('add', 2, 3)


## Using a different library for HTTP or encoding/decoding

You can override the methods of the class with your own methods.

* \_format_data takes the args and kwargs to query and converts it into a JSON blob.
* \_parse_response takes the response in the form of JSON data and creates a Python object.
* \_post takes the url and data from \_format_data and returns the response object.
