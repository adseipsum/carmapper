<<<<<<< HEAD
# CodeIgniter Composer Installer

[![Latest Stable Version](https://poser.pugx.org/kenjis/codeigniter-composer-installer/v/stable)](https://packagist.org/packages/kenjis/codeigniter-composer-installer) [![Total Downloads](https://poser.pugx.org/kenjis/codeigniter-composer-installer/downloads)](https://packagist.org/packages/kenjis/codeigniter-composer-installer) [![Latest Unstable Version](https://poser.pugx.org/kenjis/codeigniter-composer-installer/v/unstable)](https://packagist.org/packages/kenjis/codeigniter-composer-installer) [![License](https://poser.pugx.org/kenjis/codeigniter-composer-installer/license)](https://packagist.org/packages/kenjis/codeigniter-composer-installer)

This package installs the offical [CodeIgniter](https://github.com/bcit-ci/CodeIgniter) (version `3.1.*`) with secure folder structure via Composer.

**Note:** If you want to install CodeIgniter4 (under development), see <https://github.com/kenjis/codeigniter-composer-installer/tree/4.x>.

You can update CodeIgniter system folder to latest version with one command.

## Folder Structure

```
codeigniter/
├── application/
├── composer.json
├── composer.lock
├── public/
│   ├── .htaccess
│   └── index.php
└── vendor/
    └── codeigniter/
        └── framework/
            └── system/
```

## Requirements

* PHP 5.3.7 or later
* `composer` command (See [Composer Installation](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx))
* Git

## How to Use

### Install CodeIgniter

```
$ composer create-project kenjis/codeigniter-composer-installer codeigniter
```

Above command installs `public/.htaccess` to remove `index.php` in your URL. If you don't need it, please remove it.

And it changes `application/config/config.php`:

~~~
$config['composer_autoload'] = FALSE;
↓
$config['composer_autoload'] = realpath(APPPATH . '../vendor/autoload.php');
~~~

~~~
$config['index_page'] = 'index.php';
↓
$config['index_page'] = '';
~~~

#### Install Translations for System Messages

If you want to install translations for system messages:

```
$ cd /path/to/codeigniter
$ php bin/install.php translations 3.1.0
```

#### Install Third Party Libraries

[Codeigniter Matches CLI](https://github.com/avenirer/codeigniter-matches-cli):

```
$ php bin/install.php matches-cli master
```

[CodeIgniter HMVC Modules](https://github.com/jenssegers/codeigniter-hmvc-modules):

```
$ php bin/install.php hmvc-modules master
```

[Modular Extensions - HMVC](https://bitbucket.org/wiredesignz/codeigniter-modular-extensions-hmvc):

```
$ php bin/install.php modular-extensions-hmvc codeigniter-3.x
```

[Ion Auth](https://github.com/benedmunds/CodeIgniter-Ion-Auth):

```
$ php bin/install.php ion-auth 2
```

[CodeIgniter3 Filename Checker](https://github.com/kenjis/codeigniter3-filename-checker):

```
$ php bin/install.php filename-checker master
```

[CodeIgniter Rest Server](https://github.com/chriskacerguis/codeigniter-restserver):

```
$ php bin/install.php restserver 2.7.2
```

### Run PHP built-in server (PHP 5.4 or later)

```
$ cd /path/to/codeigniter
$ bin/server.sh
```

### Update CodeIgniter

```
$ cd /path/to/codeigniter
$ composer update
```

You must update files manually if files in `application` folder or `index.php` change. Check [CodeIgniter User Guide](http://www.codeigniter.com/user_guide/installation/upgrading.html).

## Reference

* [Composer Installation](https://getcomposer.org/doc/00-intro.md#installation-linux-unix-osx)
* [CodeIgniter](https://github.com/bcit-ci/CodeIgniter)
* [Translations for CodeIgniter System](https://github.com/bcit-ci/codeigniter3-translations)

## Related Projects for CodeIgniter 3.x

* [Cli for CodeIgniter 3.0](https://github.com/kenjis/codeigniter-cli)
* [ci-phpunit-test](https://github.com/kenjis/ci-phpunit-test)
* [CodeIgniter Simple and Secure Twig](https://github.com/kenjis/codeigniter-ss-twig)
* [CodeIgniter Doctrine](https://github.com/kenjis/codeigniter-doctrine)
* [CodeIgniter Deployer](https://github.com/kenjis/codeigniter-deployer)
* [CodeIgniter3 Filename Checker](https://github.com/kenjis/codeigniter3-filename-checker)
* [CodeIgniter Widget (View Partial) Sample](https://github.com/kenjis/codeigniter-widgets)
=======
[![Build Status](https://travis-ci.org/intekhabrizvi/Codeigniter-mongo-library.svg?branch=unitesting)](https://travis-ci.org/intekhabrizvi/Codeigniter-mongo-library)
=======
CIMongo - MongoDB Library for Codeigniter
=======

This library help you to use perform MongoDB based queries just like active record in CodeIgniter.

This library support
* Write Concern and Journal
* Read Preference
* Aggregation Framework
* Query Profiling

Wiki and how-to can be found here http://intekhabrizvi.github.io/mongodb-library-for-codeigniter.html 

For Code Unitesting use branch named `unitesting`
#Methods

##Insert Method
* `insert` Insert a new document into a collection
* `batch_insert` Insert multiple new documents into a collection

##Select Method
* `select` Get select fields from returned documents
* `where` OR `get_where` Where section of the query
* `where_in` Where something is in an array of something
* `where_in_all` Where something is in all of an array of * something
* `where_not_in` Where something is not in array of something
* `where_or` Where something is based on or
* `where_gt` Where something is greater than something
* `where_gte` Where something is greater than or equal to something
* `where_lt` Where something is less than something
* `where_lte` Where something is less than or equal to something
* `where_between` Where something is in between to something
* `where_between_ne` Where something is in between and but not equal to something
* `where_ne` Where something is not equal to something
* `like` Where something is search by like query
* `order_by` Order the results
* `limit` OR `offset` Limit the number of returned results
* `count` Document Count based on where query
* `distinct` Retrieve a list of distinct values for the given key across a single collection
* `find_one` Retrieve single document from collection

##Update Method
* `set` Sets a field to a value
* `unset_field` Unsets a field
* `addtoset` Adds a value to an array if doesn't exist
* `push` Pushes a value into an array field
* `pop` Pops a value from an array field
* `pull` Removes an array by the value of a field
* `rename_field` Rename a field
* `inc` Increments the value of a field
* `mul` Multiple the value of a field
* `max` Updates the value of the field to a specified value if the specified value is greater than the current value of the field
* `min` Updates the value of the field to a specified value if the specified value is less than the current value of the field.
* `update` Update a single document in a collection
* `update_all` Update all documents in a collection

##Delete Method
* `delete` Delete a single document in a collection
* `delete_all` Delete all documents in a collection

##Aggregation Method
* `aggregate` Perform aggregation query on document

##Profiling Methods
* `output_benchmark` return complete explain data for all the find based query performed

##Index Method
* `add_index` Create a new index on collection
* `remove_index` Remove index from collection
* `list_indexes` Show all index created on collections

##DB Method
* `switch_db` Switch to a different database
* `drop_db` Drops a database
* `drop_collection` Drops a collection
* `command` Perform MongoDB command

##Extra Helper
* `date` Create or convert date to MongoDB based Date

##License 
Creative Commons Attribution 3.0 License.
Codes are provided AS IS basis, i am not responsible for anything.
>>>>>>> cimongo/master
