DEVOPly CLI

DEVOPly CLI is used to deploy locally developed apps managed by DEVOPly to your remote VPS servers managed by DEVOPly. It has a few modes, either backed by using S3 cloud storage to create an archive of your site and then copying that archive to the target remote server or using GIT to deploy (note: GIT is only available in the premium version).

GIT Deployment
Using Git. This command pushes your current commits to Github or Bitbucket and then pulls those from the remote server. It may also move your database archive to the destination server using SCP and therefore will require SSH credentials set using the configure command.

S3 Deployment
Using Amazon S3. You must specify S3 keys and bucket using the configure command. This is useful if you can not access your server via SSH for some reason such as a firewall.

SCP
Using SCP supported by most SSH servers. Uses SSH so you must specify your SSH information using the configure command.

Rsync
Using a local rsync client. Rsync uses SSH so you must specify your SSH information using the configure command. Rsync must be installed on the local machine and in the application path.

deploy – deploy local site to a remote server.
list – list your local sites.
remote-list – list your remote sites.
servers – list your remote servers.
configure – creates a yaml file to describe the default deployment

database pull – pull the database from a remote server
--site-domain=example.com
--remote-server=server1.example.com

database push – push development database to a staging or production server. dangerous
--site-domain=example.com
--remote-server=server1.example.com
--configure=true

deploy – 
--site-domain=example.com
--remote-server=server1.example.com
--remote-site=staging.example.com
--method=git|s3|scp|rsync
--sync-db=true|force

configure – 
--site-domain=example.com
--remote-server=server1.example.com
--remote-site=staging.example.com
--method=git|s3
--sync-db=true|force
--s3-bucket=
--s3-secret=
--s3-key=
--ssh-key-path=
--ssh-username=

