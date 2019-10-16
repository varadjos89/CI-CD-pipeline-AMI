# fa19-team-025-ami

## Installation
    1. Subscribe to CentOS in AWS Marketplace
    2. Download Packer from https://www.packer.io/ add it to your path
    3. Install using: sudo snap install packer
    4. Check if Packer installed successfully with packer --version command
## Build AMI (Amazon Machine Image) using Packer commands
    1. Input your access key, secret key and subnet id in ami-vars file
    2. Validate template with packer validate -var-file=./ami-vars.json centos-ami.json
    3. Build template with packer build -var-file=./ami-vars.json centos-ami.json
## Launch the EC2 instance from the created AMI
    1. Once the ami is created. Generate a ssh key in a .ssh folder(should not be in download folder)
    2. Run ssh-keygen command and enter the file where you want to save the key.
    3. Note that the private key should have 600 as permission
    4. Now, navigate to the EC2 Dashboard and add key pairs.
    5. Next, in the Choose AMI tab select MyAMI from the left panel to select the ami that was just created.
    6. Next, in the Choose Instance Type tab select type as t2.micro and click on next
    7. Next, in the Configure Instance Details tab in the network section select the vpc that is already created; followed by any of its subnet, make auto-assign public    IP to be enabled.
    8. Next, in the Add Storage make sure Delete on Termination is checked
    9. Next, in the Add Tags make no changes
    10. Next, in the Configure Security Group tab setup the security group with rules of your relevance like Type SSH, Port 22, Source Custom. Add Multiple rule if         required.
    11. Next Launch Instance, do select the existing key pair added in step 4. Now click on Launch  
## Deploying the Web application on the running EC2 instance
    1. Open terminal and run following command to setup server
        ssh -i ~/.ssh/csye6225_assign_prod centos@18.209.229.251
    2. Exit the server.
    3. Now copy the war file of the web application to the centos server        using the folloscp -i ~/.ssh/csye6225_assign_prod /home/aman/csye6225/dev/ccwebapp/webapp/Recipe_Management_System/target/demo-0.0.1-SNAPSHOT.war centos@18.209.229.251:.
    4. Now again run the command of setp 1
    5. Install unzip on centos
    6. Unzip the war file
    7. Install mariadb on centos
    8. Once MariaDB is configured. Run the web application using the            following comand
        java -jar demo-0.0.1-SNAPSHOT.war
    9. Our Recipe Mangament Web application is up and running.   
## Verifying the application APIs, if they can be accessed from the IP address of EC2 instance
    1. Copy the Public DNS (IPv4) address, append it with :8080 and run in      a separate tab
    2. Apache tomcat serer is up and running.