## Introduction
This Ansible playbook generates configuration files for Splunk Add-on for AWS.
The playbook uses individual roles for each input type. Roles generate configuration files on the same host, in folder output/

|Role|Output File|Description|
| ------------- | ------------- | ------------- |
|splunk_ta_aws_iam_roles|splunk_ta_aws_iam_roles.conf|IAM Roles assumed in target AWS accounts|
|aws_description|aws_description_tasks.conf|Metadata about AWS Resources in use|
|inputs|inputs.conf|Configuration for collection of CloudWatch metrics|

## Configuration
Edit variables under group_vars/all adding the AWS AccountID and AccountName for the new AWS account
```
---
accounts:
  - accountid: 321321321321
    accountname: zebras-prod
  - accountid: 654654654654
    accountname: zebras-acc
  - accountid: 987987987987
    accountname: zebras-test
```

## Run
```
ansible-playbook site.yml
```



