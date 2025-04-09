# IWF MariaDB Docker Base Image


## Overview

This is a Docker base image for a MariaDB 11.4 container.

It's a vital part of the IWF application stack.

This image contains a default config and is largely compatible with the MySQL 5.7 release.

See our [Symfony Vagrant Docker Example Project](https://github.com/iwf-web/symfony-vagrant-docker-example) for a usage example (with MySQL).


## Links

The image is built weekly based on the official image `mariadb:11.4`.

It's available here: https://hub.docker.com/repository/docker/iwfwebsolutions/mariadb

You should always use the tag: `iwfwebsolutions/mariadb:11.4-latest`


## Versions

The X part of the version number `11.4-X` is always increased when we update the image configuration (e.g. config files).

It is NOT an indication to the patch level of the base image. It's **always** the **latest** MariaDB image of the supplied version, 
currently only `11.4`.

See the CHANGELOG to find out the details.


## Changes to the official base image

Change     | Description
-----------|--------------
timezone   | The timezone in the Linux environment is changed to the `TIMEZONE` environment variable (default: Europe/Zurich)


 
## Usage / Environment variables

Environment variable  | default value  | Description
----------------------|----------------|---------------
TIMEZONE              | Europe/Zurich  | change the timezone of the OS
MYSQL_DATABASE        | appDb          | The name of the database
MYSQL_USER            | uDb            | The name of the database user
MYSQL_PASSWORD        | SET THIS YOURSELF  | The password of the MYSQL_USER -- set this to a project specific one
MYSQL_ROOT_PASSWORD   | SET THIS YOURSELF  | The password of the MySQL root user -- set this to a project specific one


## Default config

### /etc/mysql/conf.d/iwf-default.cnf

```ini
[mysqld]
performance_schema=0  # default 1 -- 0 should decrease memory usage and performance, only enable this for debugging

innodb_buffer_pool_size=512M  # default 128M (should be about the same as the mem limit)
innodb_buffer_pool_instances=1 # default 8 (is only used if buffer_pool_size > 1GB)

skip_name_resolve=On

query_cache_type=0       # for OFF
query_cache_size=0       # to ensure QC is NOT USED

join_buffer_size=512K    # default 256k
sort_buffer_size=512K    # default 256k

slow_query_log=On
long_query_time=10

tmp_table_size=64M       # default 16M
max_heap_table_size=64M  # default 16M
```

## Extension points (change or extend configuration)

You can insert your own configuration at these points. Just mount your own config files into these directories or create a derived image from this one and change the files as needed.

Folder      | Description
------------|-------------
/etc/mysql/conf.d/   | Mount you own `.cnf` files into this directory
/etc/mysql/conf.d/iwf-default.cnf  | Overwrite or over-mount this file with your own


## Contribute!

Contribute to this project and all the other's by creating issues & pull requests.

Thanks for your help!


## Get help

Use the [issue system on Github](https://github.com/iwf-web/docker-nginx) to report errors or suggestions.

You can also write to opensource@iwf.io. We try to answer every question, but it might take some days.

 
