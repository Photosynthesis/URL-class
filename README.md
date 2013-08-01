URL-class
=========

A handy PHP class for managing target URLs and jumping over many of the common pitfalls of intra-application hyperlinks. Cool stuff.

http://www.photosynth.ca/code/url

This class allows a streamlined way of managing target URLs in web
applications. It parses the URL of the current page and breaks it down
into its constituent parts. These parts can then be individually and
reliably manipulated, and the url can be output and used in intra-application
links, preserving required GET string variables, and adding additional GET
values as needed.

This class is released under the GPL license. If you would like to use it
in proprietary applications, versions under more permissive licenses can
be provided. Write to adam@photosynth.ca.

USAGE:

<?php

$url = new url();

// On instantiation, the class detects and parses the current URL as seen by the browser (keep in mind this can be completely different than the file path, especially when URL rewriting is used. We're only concerned with client side URLS here).

// Output the url

echo $url->get();

// Output the full url with modified query string parameters

echo $url->get('action' => 'do_something_cool');

// Get the domain name

echo $url->domain();

// Get the path
echo $url->path();

// Get an array of the query variables

$query_vars = $url->query_parts;

// Delete a variable pair from the URL
$url->delete_query_pair('action');

// Set query pair
$url->set_query_pair('page_id',5);

// Define constants for each URL part

$url->define_constants();

?>
