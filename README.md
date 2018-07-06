IWF-DB -- IWF optimized docker DB images: MySQL & MariaDB
=========================================================

The Master branch should not be used.

Create new releases in the releases/* branches.

Currently there are these streams:


* releases/MYSQL-5.6     => iwfwebsolutions/mysql:5.6-latest
* releases/MYSQL-5.7     => iwfwebsolutions/mysql:5.7-latest
* releases/MARIADB-10.2  => iwfwebsolutions/mariadb:10.2-latest


New releases on the release branches should be tagged with internal version updates (changes to configuration).

During the Docker Build job the releases are automatically upgraded to the latest Docker Mysql base images (patch releases).

