﻿# ansible-s3-ftp

DESCRIPTION: This soution builds reliable FTP service using Amazon S3 bucket as a storage.
Inspired by: https://cloudacademy.com/blog/s3-ftp-server/

This manual assumes you have AWS account and EC2 instance.

TO USE ansible role, ensure that:
1. you have AWS EC2 instance and configured key pair.
2. EIP is assigned to EC2.
3. Policy like AWS managed one "AmazonS3FullAccess" added to your ec2 instance.
4. Allowed INBOUND traffic to 990/tcp, 15390:15690/tcp in EC2 secutiry group.

HOW TO USE:
1. update hosts file, use ‘sample_hosts’ as an example
2. in roles/s3-ftp-server/vars/main.yml provide your bucket name, EIP and password hash values
3. to use role in playbook, use sample_playbook’ as an example

NOTE:
The role was not designed as reusable. It didn’t fail after second run but re-usability was not properly tested.


REFERENCES:
https://cloudacademy.com/blog/s3-ftp-server/
https://github.com/s3fs-fuse/s3fs-fuse
https://github.com/s3fs-fuse/s3fs-fuse/issues/602
https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/iam-roles-for-amazon-ec2.html
https://www.digitalocean.com/community/tutorials/how-to-set-up-vsftpd-for-a-user-s-directory-on-ubuntu-16-04
https://stackoverflow.com/questions/7052875/setting-up-ftp-on-amazon-cloud-server
