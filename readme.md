[comment]: # "Auto-generated SOAR connector documentation"
# Ansible Tower

Publisher: World Wide Technology  
Connector Version: 1\.6\.0  
Product Vendor: Ansible Tower by RedHat  
Product Name: Ansible Tower  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.190  

This app launches a job template on Ansible Tower 3\.0\. The job template can be specified by its name or numeric value\. Ansible extra vars can be specified to the playbook\. After a successful launch, the app waits for the job to complete to return the job status, up to the specified dead interval iterations\. With Ansible Tower 3\.0 if extra variables need be passed, the job template must have 'Prompt on launch' checked\.

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Ansible Tower asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**tower\_instance** |  required  | string | Ansible Tower IP/Hostname
**username** |  required  | string | username
**password** |  required  | password | password

### Supported Actions  
[run job](#action-run-job) - Launches an Ansible Tower job template\.  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity\.  

## action: 'run job'
Launches an Ansible Tower job template\.

Type: **generic**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**dead interval** |  optional  | Dead interval | numeric | 
**extra vars** |  optional  | Ansible extra vars | string | 
**job template id** |  required  | Job template name or id | string | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.id | string | 
action\_result\.data\.\*\.job\_stats\.id | numeric | 
action\_result\.data\.\*\.job\_stats\.status | string | 
action\_result\.data\.\*\.job\_stats\.name | string | 
action\_result\.status | string | 
action\_result\.data\.\*\.job\_stats\.elapsed | string | 
action\_result\.message | string | 
action\_result\.parameter\.context\.artifact\_id | numeric | 
action\_result\.parameter\.extra vars | string | 
action\_result\.parameter\.dead interval | numeric | 
action\_result\.parameter\.job template id | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'test connectivity'
Validate the asset configuration for connectivity\.

Type: **test**  
Read only: **True**

This action logs into Ansible Tower using a REST API call to check validate the asset configuration\.

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output