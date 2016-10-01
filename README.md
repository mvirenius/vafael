# FacetWP ElasticPress Integration
FacetWP ElasticPress Integration plugin adds ElasticPress support for FacetWP search facets. Plugin supports multiple "ElasticPress engines", which could have their own settings like "post_type" and "search_fields". Engine settings are defined by using ElasticPress supported WP_Query arguments, when registering a new search engine.

## Requirements
- Buy, install and configure [FacetWP](https://facetwp.com/)
- Install and configure [ElasticPress](https://github.com/10up/ElasticPress) and Elasticsearch server

## Installation
- Clone or copy this repo into your plugins directory

## Default search engine
Default search engine searches all registered post types using ElasticPress' default search fields:

```php
$defaults = array(
	'post_type'     => 'any',
	'search_fields' => array(
		'post_title',
		'post_content',
		'post_excerpt',
		'taxonomies' => array( 'category', 'post_tag' ),
	)
);
```

## Register new engines

New search engines can be added by using VAFAEL()->register_engine -method in the "init" hook.
The first parameter is the name of the engine and the second parameter accepts engine's WP_Query arguments.

```php
add_action('init', function(){
	VAFAEL()->register_engine( 'ElasticPress Page search', array( 'post_type' => 'page' ) );
});
```
Registered ElasticPress engines are added to the search engine dropdown of the search facet.

## Usage
- Add a new search facet
- Select "ElasticPress Default" or one of your custom engines as a search engine
- Insert facet into your site
- Enjoy a lightning fast search
