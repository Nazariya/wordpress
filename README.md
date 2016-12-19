# WordPress Website on AWS EBS
http://docs.aws.amazon.com/getting-started/latest/wordpress/deploy-wordpress-on-aws.html

### SSH
```shell
chmod 400 drag-n-drop.pem
ssh -i drag-n-drop.pem  ec2-user@54.202.254.14
sudo -i
```

### Export WP
```shell
cd /var/app/current
ls -a -l
zip -r wordpress.zip .
```

### Export DB
```shell
mysqldump --host=mydbinstance.abcdefghijkl.us-east-1.rds.amazonaws.com --user=awsuser --password=mypassword mydb > db_backup.sql
```

### Import
```shell
wget http://OLD.SITE/db_backup.sql
mysql --host=mydbinstance.abcdefghijkl.us-east-1.rds.amazonaws.com --user=awsuser --password=mypassword mydb < db_backup.sql
```