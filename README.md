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
setup-multisite [-h | -d | -b] [-n NAME | -e DB Name] [-u MySQL user] [-t MySQL host] FQDN

Creates by default a Wordpress mysql configuration depending on required fully
qualified domain name(FQDN).

Options:
    -h help
    -d destroy and purge
    -b backup
Settings:
    -n name for the wordpress site; see also -e below
    -u mysql username, will require password
    -t mysql server hostname, if unset localhost will be used
    -e existing empty mysql database name; will replace -n

Example: You want your blog to be served from http://blog.example.com
         for user 'wordpress'.

Then run:
sudo bash setup-mysql -n wordpress blog.example.com
```
