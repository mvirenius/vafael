# Valu FacetWP ElasticPress integration (VAFAEL)
This simple plugin adds ElasticPress support for FacetWP.

## Requirements
- Buy, install and configure FacetWP
- Install and configure ElasticPress and Elasticsearch server

## Installation
- Clone or copy this repo into your plugins directory

## Register new engines

New search engines can be added by using register_engine -method.
The first parameter is the name of the engine and the second parameter accepts engine's WP_Query arguments.

```php
add_action('init', function(){
	VAFAEL()->register_engine( 'ElasticPress Page search', array( 'post_type' => 'page' ) );
});
```
