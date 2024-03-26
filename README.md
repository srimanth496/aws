Hosted a wordpress website using EC2  :

first i launched a virtual server in amazon console and  named as that  server wordpress server, by using linux commands i connected virtual server to the linux command line interface ,
In the CLI i have  written the commands for to install the  php runtime and php mysql connector ,After that Installed MySQL server,in the above my sql server and php runtime can store the details of the wordpress website.
setting the right directoraries to the wordpress website,then copy the public ip adress of the EC2 instance and serach in google we can able to see the wordpress website login page and now configure the website with credentials by creating user name , password and login sucesfully.


![Screenshot 2024-03-26 121759](https://github.com/srimanth496/aws/assets/84217751/71e5047e-2f1c-47d3-9066-ddb8097e3c82)

![Screenshot 2024-03-26 112800](https://github.com/srimanth496/aws/assets/84217751/f59a0e2d-3948-440d-9c66-f74196135cdc)

1. Install Apache server on Ubuntu
sudo apt install apache2
![Screenshot 2024-03-26 114353](https://github.com/srimanth496/aws/assets/84217751/279574bb-a001-49ac-a80f-a969301800d9)

2. Install php runtime and php mysql connector
sudo apt install php libapache2-mod-php php-mysql


4. Install MySQL server
sudo apt install mysql-server
![Screenshot 2024-03-26 114821](https://github.com/srimanth496/aws/assets/84217751/323650ee-4e68-473d-874d-a241800c1c0c)
 

5. Login to MySQL server
sudo mysql -u root

6. Change authentication plugin to mysql_native_password (change the password to something strong)
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password by 'Testpassword@123';

7. Create a new database user for wordpress (change the password to something strong)
CREATE USER 'wp_user'@localhost IDENTIFIED BY 'Testpassword@123';

8. Create a database for wordpress
CREATE DATABASE wp;

9. Grant all privilges on the database 'wp' to the newly created user
GRANT ALL PRIVILEGES ON wp.* TO 'wp_user'@localhost;

10. Download wordpress
cd /tmp
wget https://wordpress.org/latest.tar.gz

finally i configure the wordpress named as (mysamplewesite.shop) website in ec2 instance 
![Screenshot 2024-03-26 120846](https://github.com/srimanth496/aws/assets/84217751/f509580f-3c56-4a14-9c3d-d795b4eb9a61)


12. Unzip
tar -xvf latest.tar.gz

13. Move wordpress folder to apache document root
sudo mv wordpress/ /var/www/html
