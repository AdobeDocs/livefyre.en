---
description: Installing the libraries for Livefyre server-side tasks
seo-description: Installing the libraries for Livefyre server-side tasks
seo-title: Installation
solution: Experience Manager
title: Installation
uuid: f60b4cc7-178f-4a16-ba75-f1d0d171c52f
exl-id: d74f85be-14c0-4f6d-8f16-b688282c0eb0
---
# Installation{#installation}


## Java {#section_yd3_3zk_rz}

To install the Java library, add this dependency to your project’s POM:

```
<dependency> 
   <groupId>com.livefyre</groupId> 
   <artifactId>livefyre</artifactId> 
   <version>2.0.3</version> 
</dependency>
```

The Java library has dependencies on the following modules:

```
<dependency> 
   <groupId>com.sun.jersey</groupId> 
   <artifactId>jersey-client</artifactId> 
   <version>[1.18.1,)</version> 
</dependency> 
<dependency> 
   <groupId>com.google.code.gson</groupId> 
   <artifactId>gson</artifactId> 
   <version>[2.3,)</version> 
</dependency> 
<dependency> 
   <groupId>com.google.guava</groupId> 
   <artifactId>guava</artifactId> 
   <version>[18.0,)</version> 
</dependency> 
<dependency> 
   <groupId>org.apache.commons</groupId> 
   <artifactId>commons-lang3</artifactId> 
   <version>[3.0.1,)</version> 
</dependency> 
<dependency> 
   <groupId>org.bitbucket.b_c</groupId> 
   <artifactId>jose4j</artifactId> 
   <version>[0.4.1,)</version> 
</dependency> 
```

For more information, read the Java docs or see the source on [GitHub](https://github.com/Livefyre/livefyre-java-utils).

## NodeJS {#section_swj_pwq_rz}

To install the NodeJS library, run this line:

`$ npm install livefyre`

The NodeJS library has dependencies on the following modules:

```
"restler":">=3.2.0", 
"validator":"=3.5.0", 
"jsonwebtoken": ">=5.0.0" 
```

For more information, read the NodeJs docs or see the source on [GitHub](https://github.com/Livefyre/livefyre-nodejs-utils).

Links: [Restler](https://github.com/danwrong/restler), [Validator](https://www.npmjs.org/package/validator), [jsonwebtoken](https://github.com/auth0/node-jsonwebtoken).

## PHP {#section_txj_xwq_rz}

To install the PHP library with Composer, add this to your composer.json:

```
"require": { 
   "livefyre/livefyre-php-utils": "2.0.4" 
}
```

Then install using:

```
composer.phar install 

```

If you do **not** use Composer, obtain the latest version of the library using:

```
git clone https://github.com/Livefyre/livefyre-php-utils 

```

To use the library, add the following to your PHP script:

```
require_once("/path/to/livefyre-php-utils/src/Livefyre.php"); 

```

The PHP library has dependencies on the following modules:

```
"ext-json": "*", 
"rmccue/requests": ">=1.0" 
"firebase/php-jwt": ">=2.0" 
```

For more information, read the PHP docs or see the source on [GitHub](https://github.com/Livefyre/livefyre-php-utils).

Links: [ext-json](https://php.net/manual/en/book.json.php), [Requests](https://github.com/rmccue/Requests/), [PHP-JWT](https://github.com/firebase/php-jwt/tree/v2.0.0)

## Python {#section_irk_fxq_rz}

To install the Python library, run this line:

`$ pip install livefyre`

The Python library has dependencies on the following modules:

```
PyJWT >= 1.0.1  
requests >= 2.2.1  
python-dateutil >= 2.2  
enum34 == 1.0  
ordereddict == 1.1 if sys.version_info[:2] < 2.7 

```

For more information, read the Python docs or see the source on [GitHub](https://github.com/Livefyre/livefyre-python-utils).

Links: [PyJWT](https://github.com/progrium/pyjwt), [Requests](https://github.com/kennethreitz/requests), [Python-Dateutil](https://pypi.python.org/pypi/python-dateutil), [Enum34](https://pypi.python.org/pypi/enum34), [OrderedDict](https://pypi.python.org/pypi/ordereddict)

## Ruby {#section_fv2_tzq_rz}

To install the Ruby library, add this line to your application’s Gemfile:

```
gem 'livefyre' 

```

Or install it yourself:

`$ gem install livefyre`

The Ruby library has dependencies on the following modules:

```
"jwt", '~> 1.4', ">= 1.4.1"  
"rest-client", '~> 1.8', ">= 1.8.0"  
"addressable", '~> 2.3', ">= 2.3.6" 
```

For more information, read the Ruby docs or see the source on [GitHub](https://github.com/Livefyre/livefyre-ruby-utils).

Links: [Ruby JWT](https://github.com/firebase/php-jwt/tree/v2.0.0), [REST Client](https://github.com/rest-client/rest-client/), [Addressable](https://github.com/sporkmonger/addressable)
