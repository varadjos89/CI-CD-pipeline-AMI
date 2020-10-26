# fa19-team-025-ami

## Installation
    1. Subscribe to CentOS in AWS Marketplace
    2. Download Packer from https://www.packer.io/ add it to your path
    3. Install using: sudo snap install packer
    4. Check if Packer installed successfully with packer --version command

## Build AMI (Amazon Machine Image) using Packer commands on-Premise
    1. Input your access key, secret key and subnet id in ami-vars file
    2. Validate template with packer validate -var-file=./ami-vars.json centos-ami.json
    3. Build template with packer build -var-file=./ami-vars.json centos-ami.json

## Build AMI (Amazon Machine Image) using Packer using CI/CD pipeline(CircleCI)
    1. CircleCI file has already been configured with all the required commands
    
