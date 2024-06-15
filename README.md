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

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/09cfe8b8-2266-422c-894b-6fbb04d4457c)

Sample Application Overview in the Local Environment :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/14a31e6b-b877-4e3e-9b77-2157c22b8db0)

Connecting the EC2 Instance to Local Ubuntu Machine :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/3406d5de-4f07-4fc3-8014-c6cf8b2a7a32)

Editing the Inbound Rules :

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/7788eea1-b976-4a90-920a-219d9233d2e1)

Final Output : (Exposing the Node JS Application Globally)

![image](https://github.com/vighas-ks-16/NodeJS-App-on-AWS/assets/107311113/875c903d-d3ba-4960-a2ff-03804700892d)






### Thus the Project has been successfully deployed on AWS 🎉
