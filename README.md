#  PHP CS Fixer - Laravel Coding Style Ruleset 

This package allows you to use the set of rules for [PHP CS Fixer](https://github.com/FriendsOfPhp/PHP-CS-Fixer) created and recommended by [Laravel Shift](https://laravelshift.com/).

You can find the **original and official** source of the ruleset in [this gist](https://gist.github.com/laravel-shift/cab527923ed2a109dda047b97d53c200).


## Installation
You can install the ruleset via composer using the following command:

```sh
composer require --dev kartikkapatel/php-style
```

This package will also require the `friendsofphp/php-cs-fixer` package.

## Usage
This package only gives you easy access to the recommended ruleset. The common and usual PHP-CS-Fixer setup
is still required:

In case you don't have one, create your `.php_cs.dist` file in project root folder.

```sh
touch .php_cs.dist
```

Put your `Finder` config inside. This will tell PHP-CS-Fixer where to run.

Usually, for a Laravel Project this is the config:

```php
<?php

$finder = PhpCsFixer\Finder::create()
  ->in([
    __DIR__.'/app',
    __DIR__.'/config',
    __DIR__.'/database',
    __DIR__.'/resources',
    __DIR__.'/routes',
    __DIR__.'/tests',
  ])
  ->name('*.php')
  ->notName('*.blade.php')
  ->ignoreDotFiles(true)
  ->ignoreVCS(true);    

return PhpStyleFixer\styles($finder);               

```

Run your fixer.

```sh
./vendor/bin/php-cs-fixer fix
```

Run on CI

```sh
./vendor/bin/php-cs-fixer fix --dry-run
```


## Resources

- Sharing PHP-CS-Fixer rules across projects and teams. [Laravel News Article](https://laravel-news.com/sharing-php-cs-fixer-rules-across-projects-and-teams)
- Laravel Shift Recommended Coding Ruleset. [Gist](https://gist.github.com/laravel-shift/cab527923ed2a109dda047b97d53c200) - [Shift](https://laravelshift.com/)