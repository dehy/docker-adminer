# dehy/adminer

[![](https://images.microbadger.com/badges/image/dehy/adminer.svg)](https://microbadger.com/images/dehy/adminer "Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/dehy/adminer.svg)](https://microbadger.com/images/dehy/adminer "Get your own version badge on microbadger.com")

[Adminer](http://www.adminer.org/en/) is a full-featured database management
tool for the web. It is a lightweight alternative to setting up phpMyAdmin.
This is a very minimalist [docker](https://www.docker.com) image that eases setup.

![](http://www.adminer.org/static/designs/hever/screenshot.png)

See also [online demo](http://adminer.sourceforge.net/adminer.php?username=).

## Usage

This docker image is available as an [automated build on the docker registry](https://hub.docker.com/r/dehy/adminer/).

The following databases are supported by this docker image:

- MySQL
- PostgreSQL
- SQLite
- SimpleDB
- ElasticSearch
- MongoDB

Unsupported databases (TODO) :

- MS SQL
- Oracle
- Firebird

The recommended way to run this container looks like this:

```bash
$ docker run --link=mysql:mysql -d -p 80:80 dehy/adminer
```

The above example exposes the Adminer webinterface on port 80, so that you can now browse to http://localhost/

This is a rather common setup following docker's conventions:

* `--link={database_container}:{alias}` will link a separate *database_container* (MySQL, PostgreSQL, ...) to this container, thus make possible to connect to it via adminer with *alias* hostname
* `-d` will run a detached instance in the background
* `-p {OutsidePort}:80` will bind the webserver to the given outside port
* `dehy/adminer` the name of this docker image

## Docker Cloud

[![Deploy to Docker Cloud](https://files.cloud.docker.com/images/deploy-to-dockercloud.svg)](https://cloud.docker.com/stack/deploy/?repo=https://github.com/dehy/docker-adminer)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fdehy%2Fdocker-adminer.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fdehy%2Fdocker-adminer?ref=badge_shield)


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fdehy%2Fdocker-adminer.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fdehy%2Fdocker-adminer?ref=badge_large)