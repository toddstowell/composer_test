# Composer Install Code

The enclosed code allows SE to use composer to build a WordPress instance quickly. Composer files will be used to deliver sites to OCIO for website hosting.

## Structure

- .gitignore
- composer.json
- README.md

### .gitignore

Within the .gitignore file, we need to exclude some of these components from the core. However, we may need to adjust this for our custom themes, which we need to figure out how to host.

```
/wp-config.php
/wordpress/
/wp-content/
/vendor/
```

### composer.json

The attached composer.json file is a snapshot in time. I believe we'll need to adjust these as new versions of themes, plugins, or the core of WordPress is released.

```
{
    "description": "Default Site Installer",
    "require": {
            "johnpbloch/wordpress": ">=5.5",
            "wpackagist-plugin/akismet": "^4.1.6",
            "wpackagist-plugin/block-lab": "^1.5.6",
            "wpackagist-plugin/classic-editor": "^1.6",
            "wpackagist-plugin/google-sitemap-generator": "^4.1.1",
            "wpackagist-plugin/redirection": "^4.8",
            "wpackagist-plugin/wordpress-seo": "^14.8",
            "wpackagist-theme/twentytwenty": "*"
	},
	"extra": {
	        "installer-paths": {
	            "wp-content/plugins/{$name}/": [
	                "type:wordpress-plugin"
	            ],
	            "wp-content/themes/{$name}/": [
	                "type:wordpress-theme"
	            ]
	        },
	        "wordpress-install-dir": "wordpress"
	},
	"repositories": [
	        {
	            "type": "composer",
	            "url": "https://wpackagist.org"
	        }
	]
}
```

### README.md

This is the file you're currently reading. It should be adjusted per project to highlight what plugins and themes we're using.
