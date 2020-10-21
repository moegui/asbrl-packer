ASBRL-PACKER
=========

Create a AMI using Hashicorp Packer.

Requirements
------------

None

Role Variables
--------------
- SSH_USERNAME: "ubuntu"
### AWS
- AWS_REGION: us-east-1
- AWS_AMI_NAME: "need-a-name"
- AWS_AMI_DESCRIPTION: "need-a-description"
- AWS_INSTANCE_TYPE: "t3a.micro"
- AWS_AMI_DEREGISTER: "true"
- AWS_AMI_DELETE_SNAP: "true"
- AWS_AMI_USERS: '["161535830326"]'

- AWS_AMI_FILTERS:
  - VIRTUALIZATION: "hvm"
  - ARCHITECTURE: "x86_64"
  - NAME: "ubuntu/images/hvm-ssd/ubuntu-bionic-18.04-amd64-server-*"
  - ROOT_DEVICE_TYPE: "ebs"
  - OWNERS: '["099720109477"]'
  - MOST_RECENT: "true"

- AWS_BLOCK_DEVICES:
  - DEVICE_NAME: "/dev/sda1"
  - VOLUME_SIZE: "8"
  - VOLUME_TYPE: "gp2"
  - DELETE_ON_TERMINATION: "true"


Dependencies
------------

None

Example Playbook
----------------

      - name: Generate AWS Image with Packer
        include_role:
            name: asbrl-packer
        vars:
            AWS_REGION: "us-east-1"
            AWS_AMI_NAME: "ami-name"
            AWS_AMI_DESCRIPTION: "ami description"
            AWS_INSTANCE_TYPE: "t3a.micro"
            AWS_AMI_DEREGISTER: "true"
            AWS_AMI_DELETE_SNAP: "true"
            AWS_AMI_USERS: '["161535830326"]'
            AWS_AMI_FILTERS:
            VIRTUALIZATION: "hvm"
            ARCHITECTURE: "x86_64"
            NAME: "ubuntu/images/hvm-ssd/ubuntu-bionic-18.04-amd64-server-*"
            ROOT_DEVICE_TYPE: "ebs"
            OWNERS: '["099720109477"]'
            MOST_RECENT: "true"

License
-------

BSD

Author Information
------------------

Moegui.com