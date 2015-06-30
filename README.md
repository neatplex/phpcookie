# PHPCookie
Free PHP cookie tools for neat and powerful projects!


## Documentation
PHPCookie is a tiny package for working with cookies and encrypting them.
It implemented the easy way to access and manipulating cookies with assuming security issues.

### Installation
#### Using Composer
It's strongly recommended to use [Composer](http://getcomposer.org).
If you are not familiar with Composer, The article
[How to use composer in php projects](http://www.miladrahimi.com/blog/2015/04/12/how-to-use-composer-in-php-projects)
can be useful.
After installing Composer, go to your project directory and run following command there:
```
php composer.phar require neatplex/phpcrypt
```
Or if you have `composer.json` file already in your application,
you may add this package to your application requirements
and update your dependencies:
```
"require": {
    "neatplex/phpcookie": "~1.0"
}
```
```
php composer.phar update
```
#### Using VendorLoader
If you don't use Composer you may use [VendorLoader](https://github.com/miladrahimi/vendorloader).
Copy `src` directory content in your application vendor directory,
then include the `vendorloader.php` in your application.
#### Manually
You can use your own autoloader as long as it follows [PSR-0](http://www.php-fig.org/psr/psr-0) or
[PSR-4](http://www.php-fig.org/psr/psr-4) standards.
In this case you can put `src` directory content in your vendor directory.

### Getting Started
It's so easy to use!
It uses [PHPCrypt](https://github.com/neatplex/phpcrypt) package to encrypt and decrypt data.
So if you use Composer everything will be ok otherwise you must download this package too.
After installation of this package you must inject it to Cookie class.
See the example to grasp all what you need to know:
```
use Neatplex\PHPCookie\Cookie;
use Neatplex\PHPCrypt\Crypt;

$crypt = new Crypt();
$crypt->setKey("68aa9534054f7a370853818743090ec4");
Cookie::setCrypt($crypt);
Cookie::set("Singer", "Pink Floyd");
// echo Cookie::get("Singer");
```
*   First of all, you must set your project key to the instance of `Crypt` class.
*   Second of all, you must inject Crypt object to `Cookie` static class via `Cookie::setCrypt()` method.
*   You must use `Cookie::set()` and `Cookie::get()` to set and get cookies.

### Encryption
All cookies will be encrypted.
If you set cookie via this package, you have to use this package to get it too.

### PHPCookieException
There are some situation which PHPCookieException will be thrown.
Here are methods and messages:
*   `Crypt object is not set` in `Cookie::set()` when you use this method before injecting Crypt instance to the class.
*   `Crypt object is not set` in `Cookie::get()` when you use this method before injecting Crypt instance to the class.
*   `The cookie value not exists` in `Cookie::get()` when you trying to get some cookie value which not exists.

## Contributor
*	[Milad Rahimi](http://miladrahimi.com)

## Official homepage
*   [PHPCookie](http://phpcookie.neatplex.com) (Soon!)

## License
PHPCookie is created by [Neatplex](http://neatplex.com)
and released under the [MIT License](http://opensource.org/licenses/mit-license.php).
