# How to use this image

The following environment variables are required for docker-cloud:

-	`WORDPRESS_DB_HOST=...`		(defaults to the IP and port of the linked `mysql` container)
-	`WORDPRESS_DB_NAME=...`		(defaults to "wordpress")
-	`WORDPRESS_DB_USER=...`		(defaults to "root")
-	`WORDPRESS_DB_PASSWORD=...`	(defaults to the value of the `MYSQL_ROOT_PASSWORD` environment variable from the linked `mysql` container)
-	`VIRTUAL_HOST=...`		(to use with docker-cloud automatic haproxy)

Example stack file for docker-cloud
~~~~
wordpress-demo:
  environment:
    - VIRTUAL_HOST=wp-demo.example.com
    - WORDPRESS_DB_HOST=10.11.12.13
    - WORDPRESS_DB_NAME=wpuser1
    - WORDPRESS_DB_USER=wpuser1
    - WORDPRESS_DB_PASSWORD=wppassword1
  image: 'hspotweb03/wordpress:latest'
~~~~
