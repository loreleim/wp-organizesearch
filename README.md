# Wordpress Organize Search Results
a plugin + research platform for custom organization in WP's search.php

## A simple functions.php, not case sensitive
```
function redirect_search_result() {
	if (is_search()) {
    global $wp_query;
    $s_str = $wp_query->query_vars['s'];
    foreach ($wp_query->posts as $p) {
      if (strtolower($p->post_title) == strtolower($s_str)) {
        wp_redirect(get_permalink($p->ID));
        exit();
      }
    }
  }
}
add_filter('template_redirect', 'redirect_search_result');
```


## Customizing the WPSearch Plugin (without a Pro license)

Create a file named `searchwp-customizations.php` in your plugins folder (which is ~/wp-content/plugins by default)

Paste this in the file:

```
<?php
/*
Plugin Name: SearchWP Customizations
Description: Customizations for SearchWP
Version: 1.0.0
*/

// Add all hooks and custom code here.
```

For the custom hooks and code, you can do various things like: 






[Source](https://searchwp.com/documentation/knowledge-base/creating-searchwp-customizations-plugin/)


## Bibliography
[Excluding pages from search results](https://www.wpexplorer.com/limit-wordpress-search/)

[functions.php order by postdate](https://wordpress.stackexchange.com/questions/339566/how-do-i-change-wp-search-results-order)

[Custom Search Results Order](https://searchwp.com/extensions/custom-results-order/)

[Redirect Users in Wordpress](https://firstsiteguide.com/how-to-redirect-users-in-wordpress/)
