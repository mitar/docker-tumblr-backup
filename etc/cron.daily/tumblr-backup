#!/bin/bash -e

. /dev/shm/cron-environment

if [ -n "$TUMBLR_BLOG_NAME" ]; then
  mkdir -p /tumblr-backup
  chown -Rh nobody:nogroup /tumblr-backup
  chpst -u nobody:nogroup /tumblr-utils/tumblr_backup.py --outdir=/tumblr-backup --dirs --quiet --json "$TUMBLR_BLOG_NAME"

  mkdir -p /tumblr-backup-history
  chown -Rh nobody:nogroup /tumblr-backup-history
  chpst -u nobody:nogroup /usr/bin/rdiff-backup --preserve-numerical-ids /tumblr-backup /tumblr-backup-history
fi
