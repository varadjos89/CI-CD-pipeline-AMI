# fa19-team-025-ami

## Installation
    1. Subscribe to CentOS in AWS Marketplace
    2. Download Packer from https://www.packer.io/ add it to your path
    3. Install using: sudo snap install packer
    4. Check if Packer installed successfully with packer --version command

## Steps to build AMI (Amazon Machine Image) using Packer on-Premise
    1. Input your access key, secret key and subnet id in ami-vars file
    2. Validate template with packer validate -var-file=./ami-vars.json centos-ami.json
    3. Build template with packer build -var-file=./ami-vars.json centos-ami.json

## Steps to build AMI (Amazon Machine Image) using CI/CD pipeline(CircleCI)
    1. Fork this repository to include it in your Github account.
    1. CircleCI file(config.yml) within the repository has been configured with all the required packer commands.
    2. Create an account on CircleCI using your Github account.
    3. Open CircleCI dashboard and set up your project.
    4. Insert env variables such as AWS_ACCESS_KEY, AWS_SECRET_KEY, AWS_REGION with appropriate values.
    5. Now for every change in your Github repository, CircleCI would automatically build, test and deploy AMI inside your AWS account
    6. Using this custom AMI, you can launch EC2 instances and deploy your code on it.

## ScreenShots
Create Account using Github
![Screenshot from 2020-10-26 19-35-04](https://user-images.githubusercontent.com/48415852/97239895-26167680-17c3-11eb-8964-64e537a59aa1.png)

Log In using GitHub
![Screenshot from 2020-10-26 19-35-18](https://user-images.githubusercontent.com/48415852/97239906-2b73c100-17c3-11eb-968e-5a255d12bc54.png)

CircleCI dashboard
![Screenshot from 2020-10-26 19-35-36](https://user-images.githubusercontent.com/48415852/97239911-2e6eb180-17c3-11eb-983d-f9b3a6d0686f.png)

SetUp your project and insert appropriate env variables
![Screenshot from 2020-10-26 19-35-55](https://user-images.githubusercontent.com/48415852/97239912-30d10b80-17c3-11eb-8c2b-175fa42deb92.png)

Successful Builds
![Screenshot from 2020-10-26 19-48-22](https://user-images.githubusercontent.com/48415852/97240276-3da22f00-17c4-11eb-9820-a9a358714b65.png)

Steps involved in build process
![Screenshot from 2020-10-26 19-38-30](https://user-images.githubusercontent.com/48415852/97239925-3890b000-17c3-11eb-9a33-551e1ff08a45.png)

![Screenshot from 2020-10-26 19-50-56](https://user-images.githubusercontent.com/48415852/97240403-97a2f480-17c4-11eb-8f44-75fc0d0e0f9a.png)

Successfully deployed custom AMI in AWS account
![Screenshot from 2020-10-26 19-39-24](https://user-images.githubusercontent.com/48415852/97239937-3e869100-17c3-11eb-9efc-2eaba42c41ae.png)

![Screenshot from 2020-10-26 19-39-36](https://user-images.githubusercontent.com/48415852/97239943-41818180-17c3-11eb-97b3-75af88c3d1c0.png)

