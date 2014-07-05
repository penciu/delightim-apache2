# Heroku-PHP-Apache2

Bootstrap package for the official PHP support on Heroku

PHP 5.5.14 (64-bit) with Apache 2.4.9 on Heroku

## Usage / Installation

Just copy the contents of this repository into the repository for your Heroku app and start developing your app in folder `public_html`.

## PHP extensions

 * Bzip2
 * cURL
 * FPM
 * mcrypt
 * MySQL (PDO)
 * MySQLi
 * OPcache
 * OpenSSL
 * PostgreSQL
 * PostgreSQL (PDO)
 * Readline
 * Sockets
 * Zip
 * Zlib
 * **mbstring**

You may add further extensions by specifying them in your [composer.json](composer.json) file [like this](https://devcenter.heroku.com/articles/php-support#extensions).

## Modifications to `php.ini`

| Directive               | This repository   | Heroku default    |
| ----------------------- | ----------------- | ----------------- |
| short_open_tag          | Off               | On                |
| expose_php              | Off               | On                |
| post_max_size           | 2M                | 8M                |
| file_uploads            | Off               | On                |
| max_file_uploads        | 8                 | 20                |
| log_errors              | Off               | On                |
| ignore_user_abort       | On                | Off               |
| memory_limit            | 32M               | 128M              |
| error_reporting         | E_ALL & ~E_STRICT | E_ALL & ~E_NOTICE |
| display_errors          | On                | Off               |
| session.cookie_httponly | On                | Off               |

You may revert or enhance any of these modifications by adjusting [web-boot.sh](web-boot.sh).

## Modifications to `httpd.conf`

| Directive       | This repository  | Heroku default |
| --------------- | ---------------- | -------------- |
| ServerSignature | Off              |                |
| ServerTokens    | Prod             |                |
| HostnameLookups | Off              |                |
| TraceEnable     | Off              |                |
| ServerLimit     | 32               |                |
| MaxClients      | 32               |                |
| DocumentRoot    | /app/public_html | /app           |

You may revert or enhance any of these modifications by adjusting [web-boot.sh](web-boot.sh).

## License

```
Copyright 2014 www.delight.im <info@delight.im>

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```