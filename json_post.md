# pecl/json_post

## About:

JSON POST handler.

Parse JSON request bodies into `$_POST`.

## What it does:

This tiny extension provides a PHP content type handler for JSON to PHP's form data parser. 

If the `Content-Type` of an incoming request is `application/json` or `text/json`, the JSON contents of the request body will by parsed into `$_POST`.

## Installation:

This extension is hosted at [PECL](http://pecl.php.net) and can be installed with [PEAR](http://pear.php.net)'s pecl command:

    # pecl install json_post

## Dependencies:

* ext/json

## INI Directives:

json_post.flags = 1
:	json_decode() flags
	* JSON_OBJECT_AS_ARRAY = 1
	* JSON_BIGINT_AS_STRING = 2
	* JSON_OBJECT_AS_ARRAY|JSON_BIGINT_AS_STRING = 3
	* JSON_INVALID_UTF8_IGNORE = 1048576 ; (PHP >= 7.2)
	* JSON_INVALID_UTF8_SUBSTITUTE = 2097152 ; (PHP >= 7.2)
	* JSON_THROW_ON_ERROR is ignored

json_post.onerror.response = 0
:	Send a custom HTTP response status on failure, e.g.:  
	; send `HTTP/1.1 400 Bad Request` on error  
	json_post.onerror.response = 400

json_post.onerror.warning = Off
:	Raise `E_WARNING` on failure decoding JSON when enabled.

json_post.onerror.exit = Off
:	Exit PHP without running the script on decoding failure when enabled.

## Changelog:

0. v1.1.0
	* Ignore JSON_THROW_ON_ERROR in `json_post.flags`.
	* Add `json_post.onerror.response` INI setting.
	* Add `json_post.onerror.warning` INI setting.
	* Add `json_post.onerror.exit` INI setting.
