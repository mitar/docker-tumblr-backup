This Docker image daily backups whole Tumblr blog. It keeps past versions available as well using
[rdiff-backup](http://www.nongnu.org/rdiff-backup/).

It is configured through an environment variable:
 * `TUMBLR_BLOG_NAME` – name of the Tumblr blog to backup

You should make sure you mount backup volume (`/tumblr-backup-history`) so that backup is preserved
when container is recreated. This volume contains the latest backup together with `rdiff-backup`
data for previous versions. `/tumblr-backup` volume contains only the latest backup.
