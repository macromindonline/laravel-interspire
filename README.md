laravel-interspire
==================

Interspire API Intergration Made Easy

## Installation

Add laravel-interspire to your composer.json file:

```
"require": {
  "aglipanci/interspire": "dev-master"
}
```

Use composer to install this package.

```
$ composer update
```

### Registering the Package

Register the service provider within the ```providers``` array found in ```app/config/app.php```:

```php
'providers' => array(
	// ...
	
	'Aglipanci\Interspire\InterspireServiceProvider',
)
```

Add an alias within the ```aliases``` array found in ```app/config/app.php```:


```php
'aliases' => array(
	// ...
	
	'Interspire'     => 'Aglipanci\Interspire\Facades\Interspire',
)
```

## Configuration

Create configuration file for package using artisan command

```
$ php artisan config:publish aglipanci/interspire
```

And edit the config file with your Interspire API URL, Username and Token.


## Usage

### Basic usage

To add a new Subscriber to a list you should add name, surname, email and the list id (which you get from interspire);

```php
Interspire::addSubscriberToList('John', 'Smith', 'jsmith@gmail.com', 1);
```

To delete an existing Subscriber you need only the email address:

```php
Interspire::deleteSubscriber('jsmith@gmail.com');
```

	