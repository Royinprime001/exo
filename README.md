# eXo Docker container

[![Docker Stars](https://img.shields.io/docker/stars/exoplatform/exo.svg?maxAge=2592000)]() - [![Docker Pulls](https://img.shields.io/docker/pulls/exoplatform/exo.svg?maxAge=2592000)]()

The aim of this repository is to give the configuration to run eXo Platform in a Docker containers for production purpose.

# Supported databases

Currently we only support `MySQL`.

## Configuration

The following environment variables must be passed to the container in order to work :


|    VARIABLE              |  MANDATORY  |   DEFAULT VALUE          |  DESCRIPTION
|--------------------------|-------------|--------------------------|----------------
| EXO_DB_TYPE | NO | `mysql` | we currently only support mysql
| EXO_DB_NAME | NO | `exo` | the name of the database / schema to use
| EXO_DB_USER | NO | `exo` | the username to connect to the database
| EXO_DB_PASSWORD | YES | - | the password to connect to the database
| EXO_DB_HOST | NO | `mysql` | the host to connect to the database server
| EXO_DB_PORT | NO | `3306` | the port to connect to the database server
| EXO_DATA_DIR | NO | `/srv/exo` | the directory to store eXo Platform data

### LDAP / Active Directory

The following environment variables should be passed to the container in order to configure the ldap connection pool :

|    VARIABLE              |  MANDATORY  |   DEFAULT VALUE          |  DESCRIPTION
|--------------------------|-------------|--------------------------|----------------
| EXO_LDAP_POOL_DEBUG      | NO | - | the level of debug output to produce. Valid values are "fine" (trace connection creation and removal) and "all" (all debugging information).
| EXO_LDAP_POOL_TIMEOUT    | NO | `60000` | the number of milliseconds that an idle connection may remain in the pool without being closed and removed from the pool.
| EXO_LDAP_POOL_MAX_SIZE   | NO | `100` | the maximum number of connections per connection identity that can be maintained concurrently.

## License

The eXo Platform license file location must be `/etc/exo/license.xml`
