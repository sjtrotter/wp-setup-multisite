# wp-setup-multisite
A short helper script to assist with a multisite wordpress setup

```bash
setup-mysql [-h | -d | -b] [-n NAME | -e DB Name] [-u MySQL user] [-t MySQL host] FQDN

Creates by default a Wordpress mysql configuration depending on required fully
qualified domain name(FQDN).

Options:
    -n name for the wordpress site; see also -e below
    -h help
    -d destroy and purge
    -b backup
    -u mysql username, will require password
    -t mysql server hostname, if unset localhost will be used
    -e existing empty mysql database name; will replace -n

Example: You want your blog to be served from http://blog.example.com
         for user 'wordpress'.

Then run:
sudo bash setup-mysql -n wordpress blog.example.com
```
