# wp-setup-multisite
A helper script to assist with a multisite wordpress setup.

This is adapted and rewritten from the base Debian install package, from the 
file `/usr/share/doc/wordpress/examples/setup-mysql`.

We are supporting the following scenarios:
1. Creating a new wordpress site with bare wp-content and new database
2. Destroying a wordpress site; dropping tables in database, deleting data
3. Backing up previous database and config

You should start with a clean Wordpress install to ensure nothing has been 
previously written in the wp-content directory; if not, you'll be copying 
the things you already installed, like plugins and themes. (Not a big deal.)

## Usage

```bash
setup-multisite [-h|-d|-b] [-v] [-f] [-n NAME][-u USER][-p PASS]
        [-N HOST][-T PORT][-U USER][-P PASS]

Creates by default a Wordpress configuration depending on required fully
qualified domain name (FQDN).

Options:
    -h    show this help and exit
    -d    destroy site (drop database, delete config)
    -b    backup site (dump database, save config to .tar.gz)
    -V    show version
    -v    increase verbosity
    -f    force - skips prompts, allows operation when it might fail
          i.e: config exists, config not written by script

Wordpress Settings: (auto-generated if not given)
    -n NAME     mysql database for this wordpress instance
    -u USER     mysql username for this wordpress instance
    -p PASS     mysql password for this wordpress instance

Database Settings: (assumed localhost/root/no password if not given)
    -N HOST     mysql server hostname (for non-standard database)
    -T PORT     mysql server port (for non-standard database)
    -U USER     mysql admin username (for non-standard database)
    -P PASS     mysql admin password (for non-standard database)

Examples:
    create database and config for blog.example.com:
        bash setup-multisite blog.example.com
    
    backup database and config for blog.example.com with debugging enabled:
        bash setup-multisite -bv blog.example.com

    force destroy database and config with no prompt for blog.example.com:
        bash setup-multisite -df blog.example.com
```
