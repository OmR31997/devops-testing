## EC2 - Elastic Compute Cloud

This allow us to launch virtual machine.

- Virtual servers in Amazon's cloud
- Scalable compute capacity on-demand
- Pay-as-you-go pricing model
- Supports multiple instance types (general purpose, compute optimized, memory optimized, storage optimized)
- Integrates with other AWS services (S3, RDS, VPC, IAM)

## S3 - Simple Storage Service

- Object storage service for storing and retrieving any amount of data
- Scales automatically to handle high traffic and large amounts of data
- Provides high durability (99.999999999%) through data replication across multiple facilities
- Supports various storage classes (Standard, Infrequent Access, Glacier) for cost optimization
- Integrates with other AWS services (EC2, Lambda, CloudFront, etc.)

## Pm2 Project Build

1: git clone https://github.com/OmR31997/book-library-system.git
2: go to that app location
3: sudo apt update
4: sudo apt install nginx -y
5: nginx -v
6: sudo apt install npm
7: npm install
8: npm run build
9: set customer port inside aws then connect
10: sudo sytermctl start nginx => Used for serving static files and reverse proxying requests
11: sudo systemctl start nginx
12: sudo systemctl enable nginx
13: sudo systemctl status nginx
14: sudo nano /etc/nginx/sites-available/default
15: Set => location / {
proxy_pass http://localhost:3000;

    proxy_http_version 1.1;

    proxy_set_header Upgrade $http_upgrade;
    proxy_set_header Connection "upgrade";

    proxy_set_header Host $host;

    proxy_cache_bypass $http_upgrade;

} => Ctr + O, then Enter, then Ctr + X
16: sudo nginx -t => To test of nginx
17: sudo systemctl restart nginx
18: pm2 list
19: pm2 restart 0

## Ubuntu Linux Commands

- sudo apt update
  Description: To update app package manager.

1: Way (Install/Uninstall Docker)

- sudo apt install docker.io
  Description: To install docker depedencies.

- sudo apt remove docker.io -y
  Description: To remove docker depedencies.

2: Way

- Visit: https://docs.docker.com/engine/install/ubuntu/

# Install Docker CE

- sudo apt-get update
  Description: To update package index.

- sudo apt-get install docker-ce
  Description: To install Docker Community Edition.

- sudo docker pull <image_name>
  Description: To pull a Docker image from a registry.

- sudo docker run -it -d <image_name>
  Description: To run a Docker container in detached mode.

- sudo docker run -it -d --name <container_name> <image_name>
  Description: To run a named Ubuntu container in detached mode.

- sudo docker run -it -d --name <container_name> -p <host_port>:<container_port> <imager_name>
  Description: To run a named Ubuntu container with port mapping (host_port:80).

- sudo docker run -it -d --name publshed_container -p 80:80 ubuntu
