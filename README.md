# NodeJS-App-on-AWS
Deploying and Exposing a Node JS Application on Amazon EC2

1. Clone this project
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
3. Initialise and start the project
```
npm install
npm run start
```

### Set up an AWS EC2 instance

1. Create an IAM user & login to your AWS Console
    - Access Type - Password
    - Permissions - Admin
2. Create an EC2 instance
    - Select an OS image - Ubuntu
    - Create a new key pair & download `.pem` file
    - Instance type - t2.micro
3. Connecting to the instance using ssh
```
ssh -i instance.pem ubunutu@<IP_ADDRESS>
```

### Configuring Ubuntu on remote VM

1. Updating the outdated packages and dependencies
```
sudo apt update
```
3. Install Git  
4. Configure Node.js and `npm`

### Deploying the project on AWS

1. Clone this project in the remote VM
```
git clone https://github.com/verma-kunal/AWS-Session.git
```
2. Setup the following environment variables - `(.env)` file
```
DOMAIN= ""
PORT=3000
STATIC_DIR="./client"

PUBLISHABLE_KEY=""
SECRET_KEY=""
```
> For this project, we'll have to set up an [Elastic IP Address](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/elastic-ip-addresses-eip.html) for our EC2 & that would be our `DOMAIN`

3. Initialise and start the project
```
npm install
npm run start
```

> NOTE - We will have to edit the **inbound rules** in the security group of our EC2, in order to allow traffic from our particular port
### PROJECT WORKFLOW :

Backend Initialization :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/a74d2798-d7ec-403e-ad02-1513c6125adb)


Sample Application Overview in the Local Environment :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/6d245816-c3dd-446c-a0f7-5009e15c4d35)


Connecting the EC2 Instance to Local Ubuntu Machine :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/bc2776bd-516e-4c10-a866-7401b936b1e9)


Editing the Inbound Rules :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/4e92e48c-acbe-4fc2-ab35-cdf68e0e05b8)


Final Output : (Exposing the Node JS Application Globally)

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/30ecb4d5-5396-44e4-a845-345ebadd85eb)







### Thus the Project has been successfully deployed on AWS 🎉
