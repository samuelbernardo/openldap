# OpenLDAP

Goal: deploy OpenLDAP with mirror mode replication

- configure CI with Travis
- do orquestration using terraform with provider libvirt (or AWS EC2 as suggested in [1]) and provisioner ansible
- base image: CentOS 7
- ldap setup and configuration using ansible

Terraform will allow the code independency from the provider. Ansible provisioner will automate the deployment and configuration using the modules such as [2] and [3].

[1] https://dev.to/frosnerd/continuous-delivery-on-aws-with-terraform-and-travis-ci-3914

[2] https://docs.ansible.com/ansible/latest/modules/modules_by_category.html

[3] https://github.com/unchained-capital/ansible-ldap-modules


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

Reference: https://confluence.atlassian.com/bitbucket/use-smart-commits-298979931.html
