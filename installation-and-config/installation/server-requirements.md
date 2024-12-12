---
description: Use this checklist to setup your server.
---

# Server Requirements

### Minimum System Requirements

#### PHP Requirements

* PHP >= 8.2
* BCMath PHP Extension
* Ctype PHP Extension
* cURL PHP Extension
* DOM PHP Extension
* Fileinfo PHP Extension
* JSON PHP Extension
* Mbstring PHP Extension
* OpenSSL PHP Extension
* PCRE PHP Extension
* PDO PHP Extension
* Tokenizer PHP Extension
* XML PHP Extension

#### Web Server

One of the following:

* Apache 2.4+ with `mod_rewrite` enabled
* Nginx 1.18+

#### Database

One of the following:

* MySQL 8.0+
* PostgreSQL 10.0+

#### Additional Software (For CI pipeline)

* Composer 2.0+
* Node.js 16+
* NPM 8+ or Yarn 1.22+



### PHP Configuration

```ini
memory_limit = 256M
max_execution_time = 60
upload_max_filesize = 50M
post_max_size = 50M
max_input_vars = 1500
```

### Required PHP Extensions Configuration

```ini
extension=bcmath
extension=ctype
extension=curl
extension=dom
extension=fileinfo
extension=json
extension=mbstring
extension=openssl
extension=pdo
extension=tokenizer
extension=xml
```

###



