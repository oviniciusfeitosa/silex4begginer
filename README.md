# Sikex4begginer

##About
Easy way to learn a little about Silex and use this micro framework as service.

## Installing via Composer

Follow the steps below :
```php
  $ mkdir api-test-silex           # Create a directory for our test
  $ cd api-test-silex              # Enter in new folder created
  $ composer require silex/silex   # set Silex as dependency via Composer
```
## Setting up

- Now we need to use a Silex Application as object to do what we want. So lets start creating a 'index.php' file:
```php
  $ sudo nano index.php
```
- Then put the contents below inside him:
```php
  <?php
  require_once __DIR__.'/vendor/autoload.php';
  $app = new Silex\Application();
  $app->get('/myroute/{name}', function($name) use($app) {
      return json_encode(
		  [
  			"name" => $name,
			  "phone" => '99988-8855',
  		]
	  );
  });
  $app->run(); 
```
## Executing
- For this scenario, we will use PHP Built-in web server. Use the command below:
```php
  $ php -S 127.0.0.1:8888 index.php
```
- Now access the url http://127.0.0.1:8888/myroute/YourName
- If it works fine, uou will see your some information as json.

## Understanding

- This path `require_once __DIR__.'/vendor/autoload.php';` require Composer Autoloader;
- `$app = new Silex\Application();` here we create  a object of Silex Application;
- `$app->get('/myroute/{name}', function($name) use($app) {` here we set the route "/ionic/{name}", where the {name} will be send as parameter.
- And here `return json_encode(... ` we have our return for this route

## Finish
Simple, no?
Any question, send me a [mail](viniciusfesil@gmail.com)! 
