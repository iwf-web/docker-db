IWF-MYSQL -- IWF optimized docker images
========================================

The Master branch should not be used.

Create new releases in the releases/* branches.

Currently there are two streams:


releases/MYSQL-5.6
releases/MYSQL-5.7


New releases on the release branches should be tagged with internal version updates (changes to configuration).

During the Docker Build job the releases are automatically upgraded to the latest Docker Mysql base images (patch releases).

