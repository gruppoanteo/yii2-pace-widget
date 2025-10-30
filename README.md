## Yii2 Pace Widget

A Yii2 widget that shows an automatic page loading progress bar powered by the
**[Pace](https://github.com/HubSpot/pace)** JavaScript library.

### What does Pace do?
Pace automatically monitors AJAX requests, event loop lag, document readiness,
and selected elements on the page to determine and display loading progress. On
AJAX navigation, it restarts automatically.

For details about Pace itself, see the official docs: **[github.hubspot.com/pace](http://github.hubspot.com/pace/)**.


## Requirements

- **Yii 2** (`yiisoft/yii2` ~2)
- **Pace assets** (`bower-asset/pace`)


## Installation

Install via [Composer](https://getcomposer.org/):

```bash
composer require anteo/yii2-pace-widget:^0.0.2
```

Or add it manually to the `require` section of your `composer.json` and then run `composer update`:

```json
{
  "require": {
    "anteo/yii2-pace-widget": "^0.0.2"
  }
}
```


## Usage

Add the widget to any view or layout to enable the progress bar:

```php
<?php
echo anteo\yii\widgets\pace\Pace::widget();
```

### Options
The widget accepts the following options:

- **color**: The Pace theme color folder to use (default: `blue`).
- **theme**: The Pace theme name to use (default: `flash`).
- **paceOptions**: An associative array mapped to `window.paceOptions` to configure Pace behavior. See the [Pace documentation](http://github.hubspot.com/pace/) for all available options.

Examples:

```php
<?php
echo anteo\yii\widgets\pace\Pace::widget([
    'color' => 'green',
    'theme' => 'flash',
]);
```

```php
<?php
echo anteo\yii\widgets\pace\Pace::widget([
    'color' => 'blue',
    'theme' => 'flash',
    'paceOptions' => [
        'ajax' => false,
        'document' => false,
    ],
]);
```

Notes:
- The widget registers `pace.min.js` in the document head and sets `window.paceOptions` if provided.
- CSS is resolved from Pace’s distributed themes as `themes/{color}/pace-theme-{theme}.css`. Ensure that the corresponding theme exists in the installed Pace package.


## License

BSD 3-Clause. See `LICENSE` for details.
