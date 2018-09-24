# openldap

Goal: deploy OpenLDAP with mirror mode replication

- configure CI with Travis
- do orquestration using terraform with provider libvirt (or AWS EC2 as suggested in [1]) and provisioner ansible
- base image: CentOS 7
- ldap setup and configuration using ansible

Terraform will allow the code independency from the provider. Ansible provisioner will automate the deployment and configuration using the modules such as [2] and [3].

[1] https://dev.to/frosnerd/continuous-delivery-on-aws-with-terraform-and-travis-ci-3914

[2] https://docs.ansible.com/ansible/latest/modules/modules_by_category.html

[3] https://github.com/unchained-capital/ansible-ldap-modules
