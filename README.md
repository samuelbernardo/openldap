# OpenLDAP

Goal: deploy OpenLDAP with mirror mode replication and also proxy mode for replicas distribution

- configure CI with Travis
- do orquestration using terraform with provider libvirt (or AWS EC2 as suggested in [1]) and provisioner ansible
- base image: CentOS 7
- ldap setup and configuration using ansible
- ldap instance with meta backend to allow multiple domains to be accessible from the same ldap client
- test ldap client with ssh authentication using ssh keys
- test ldap client with saml authentication using ldap sasl pam module

Terraform will allow the code independency from the provider. Ansible provisioner will automate the deployment and configuration using the modules such as [2].

[1] https://dev.to/frosnerd/continuous-delivery-on-aws-with-terraform-and-travis-ci-3914

[2] https://docs.ansible.com/ansible/latest/modules/modules_by_category.html

## Related projects

[3] https://github.com/unchained-capital/ansible-ldap-modules

[4] https://docs.ansible.com/ansible/latest/modules/ldap_attr_module.html#ldap-attr-module

[5] https://docs.ansible.com/ansible/latest/modules/ldap_entry_module.html#ldap-entry-module

[6] https://docs.ansible.com/ansible/latest/modules/ldap_passwd_module.html#ldap-passwd-module

[7] https://github.com/kbrebanov/ansible-openldap

[8] https://github.com/debops/ansible-slapd

[9] https://github.com/mrlesmithjr/ansible-openldap

[10] https://github.com/bennojoy/openldap_server

[11] https://github.com/gronke/ansible-openldap

[12] https://github.com/CSCfi/ansible-role-openldap

## OpenLDAP documentation

[13] http://www.openldap.org/doc/admin24/guide.html

[14] https://www.openldap.org/doc/admin24/replication.html

[15] https://www.openldap.org/doc/admin24/backends.html

[16] http://www.openldap.org/software/man.cgi?query=slapd-ldap&sektion=5&apropos=0&manpath=OpenLDAP+2.4-Release

[17] http://www.openldap.org/software/man.cgi?query=slapo-rwm&sektion=5&apropos=0&manpath=OpenLDAP+2.4-Release

### OpenLDAP meta backend

[18] http://www.openldap.org/software/man.cgi?query=slapd-meta&apropos=0&sektion=0&manpath=OpenLDAP+2.4-Release&format=html

[19] https://serverfault.com/questions/106869/how-can-i-proxy-multiple-ldap-servers-and-still-have-grouping-of-users-on-the-p

[20] https://github.com/kgalal/meta-ldap

[21] http://blog.oddbit.com/2010/02/16/merging-directories-with-openldap-meta/

[22] https://gist.github.com/pbruna/7229c3e99dd4bf57b73c

[23] https://www.pixelstech.net/article/1509203627-OpenLDAP-Proxy----Introduction

[24] https://www.pixelstech.net/article/1509263631-OpenLDAP-Proxy----slapd-conf

[25] https://www.pixelstech.net/article/1509756599-OpenLDAP-Proxy----Installation-and-configuration

[26] https://www.pixelstech.net/article/1509784887-OpenLDAP-Proxy----Tricks-and-tips

[27] https://www.pixelstech.net/article/1517623155-OpenLDAP-Proxy----rwm-map-vs-map

## Terraform

[28] https://www.terraform.io/docs/provisioners/index.html

[29] https://www.terraform.io/docs/providers/

### Terraform Ansible provisioner

[30] https://github.com/jonmorehouse/terraform-provisioner-ansible (discontinued)

[31] https://github.com/radekg/terraform-provisioner-ansible

[32] https://github.com/adammck/terraform-inventory

### Terraform Ansible provider

[33] https://github.com/nbering/terraform-provider-ansible/

[34] https://nicholasbering.ca/tools/2018/01/08/introducing-terraform-provider-ansible/

[35] https://docs.ansible.com/ansible/devel/modules/terraform_module.html

[36] https://github.com/ramitsurana/terraform-ansible-setup

[37] https://github.com/nbering/terraform-inventory/

[38] https://docs.ansible.com/ansible/latest/user_guide/intro_dynamic_inventory.html

### Terraform LDAP provider

[39] https://devhub.io/repos/Pryz-terraform-provider-ldap

[40] https://github.com/Pryz/terraform-provider-ldap

[41] https://github.com/mevansam/terraform-provider-ldap

## OpenLDAP SASL

### SAML authentication

[42] https://github.com/shoaibali/crudesaml

[43] https://github.com/ck-ws/pam-script-saml

[44] https://www.keycloak.org/docs/3.0/server_admin/topics/user-federation/sssd.html

[45] https://www.keycloak.org/docs/3.0/index.html

[46] https://www.keycloak.org/docs/3.2/server_admin/topics/identity-broker/saml.html

## JIRA Smart Commits

Create smart  commits with the following syntax

- comment: <ignored text> <ISSUE_KEY> <ignored text> #comment <comment_string>
- time: <ignored text> <ISSUE_KEY> <ignored text> #time <value>w <value>d <value>h <value>m <comment_string>
- transitions: <ignored text> <ISSUE_KEY> <ignored text> #<transition_name> #comment <comment_string>
 
 Examples:

`JRA-123 #time 2d 5h #comment Task completed ahead of schedule #resolve`

Logs 2 days and 5 hours of work against issue JRA-123, adds the comment 'Task completed ahead of schedule', 
and resolves the issue.

`JRA-123 JRA-234 JRA-345 #resolve #time 2d 5h #comment Task completed ahead of schedule`

Logs 2 days and 5 hours of work against issues JRA-123, JRA-234 and JRA-345, adds the comment 
'Task completed ahead of schedule' to all three issues, and resolves all three issues.

Multiple issue keys must be separated by whitespace or commas.

### References

[47] https://confluence.atlassian.com/bitbucket/use-smart-commits-298979931.html
