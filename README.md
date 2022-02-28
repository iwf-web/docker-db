IWF-DB -- IWF optimized docker DB images: MySQL & MariaDB
=========================================================

The Master branch is empty and should not be used.

See details in the README.md of following branches:

- [releases/MYSQL-5.7](https://github.com/iwf-web/docker-db/tree/releases/MYSQL-5.7) (Support until 10/2023)
- [releases/MYSQL-8.0](https://github.com/iwf-web/docker-db/tree/releases/MYSQL-8.0) (Support until 04/2026)
- [releases/MARIADB-10.2](https://github.com/iwf-web/docker-db/tree/releases/MARIADB-10.2) (Support until 05/2022)
- [releases/MARIADB-10.5](https://github.com/iwf-web/docker-db/tree/releases/MARIADB-10.5) (Support until 06/2025)

New releases on the release branches should be tagged with internal version updates (changes to configuration).

During the weekly Docker Build job the releases are automatically upgraded to the latest Docker base images (patch releases).
