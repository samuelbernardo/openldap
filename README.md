# OpenLDAP

Goal: deploy OpenLDAP with mirror mode replication

- configure CI with Travis
- do orquestration using terraform with provider libvirt (or AWS EC2 as suggested in [1]) and provisioner ansible
- base image: CentOS 7
- ldap setup and configuration using ansible

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

[13] https://www.openldap.org/doc/admin24/replication.html

## Ansible and Terraform

[14] https://docs.ansible.com/ansible/devel/modules/terraform_module.html
[15] https://github.com/ramitsurana/terraform-ansible-setup

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

[15] https://confluence.atlassian.com/bitbucket/use-smart-commits-298979931.html
