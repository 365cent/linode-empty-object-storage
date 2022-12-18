# linode-empty-object-storage

This script require linode-cli installed and logged in.

Since Linode buckets require them to be empty before deleting. This script was written for your convenience. Replace `$BUCKET_NAME` with the name of your bucket.

```bash
linode-cli obj ls $BUCKET_NAME | awk '{print $NF}' | while read i; do linode-cli obj rm $BUCKET_NAME $i; done
```
