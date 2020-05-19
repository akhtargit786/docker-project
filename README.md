# docker-project
In this project i used Infrastructure as a code (IAC) and create a next cloud web app 

Technology used 
I am using the docker host on AWS EC2 instance 
I am creating the ec2 instance by using ansible-playbook
Playbooks are the basis for a really simple configuration management and multi-machine deployment system, unlike any that already exist, and one that is very well suited to deploying complex applications.

creating a ansible playbook with command 
vim awsinstance.yml

- hosts: localhost
  tasks:
    - ec2:
       aws_access_key: ************************
       aws_secret_key: ******************************
       key_name: ansible-key
       group: ansible-sg
       instance_type: t2.micro
       image: ami-04dfjgd7cend
       wait: yes
       wait_timeout: 500
       count: 1
       instance_tags:
          name: prod-instance
       monitoring: yes
       region: ap-south-1
       vpc_subnet_id: subnet-012n2
       assign_public_ip: yes
       
Now run the command 
ansible-playbook awsinstance.yml

                                   


