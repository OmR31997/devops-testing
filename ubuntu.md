# To redirect dev.pem location

- cd /mnt/d/Ez_Softech/AWS_CONFIG

# Set permissions for SSH key

chmod 400 "dev.pem"

# Connect to EC2 instance

ssh -i "dev.pem" ubuntu@ec2XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

# To count all installed applications

- dpkg --get-selections | wc -l

# To see all installed applications

- dpkg --get-selections
