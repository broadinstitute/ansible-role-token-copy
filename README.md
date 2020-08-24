# ansible-role-token-copy

#### Overview
 This will copy down a folder with rsync (`gsutil rsync` will not do an individual files). I choose to use rysnc over `gsutil cp` because rsync does a md5sum check before trying to copy and will not copy if the md5sums match.

#### Default values
```
---
bucket_path: gs://test-tokens/
gcloud_project: test
folder: test1
dest_path: /tmp/
```
###### Note: the above values will need trailing slashes for `bucket_path` and `dest_path`. `folder` will not need a trailing slash at the end.

#### Sample playbook
```
---
- hosts: localhost
  roles:
  - role: ansible-role-token-copy
  ```
