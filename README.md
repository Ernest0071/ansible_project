# Billbox Ansible Playbook

All ansible playbook, variables and script required to:

- Deploy or Redeploy existing and new containers
- Install all the databases (Mongo & Mysql) needed to run billbox
- Configure and keep up to date all forward & reverse proxy settings
- Configure uptime monitoring of upstream partners
- Configure shipping of logs from proxy instances to rapid7 insightops


Introduction
-------------

The purpose of this documentation is to help establish a working model on how to setup local machine and how to successfully run Billbox safely. This documentation
covers the following environment:

- prod: (Production)
- uat: (User Acceptance Test)
- test: (Testing environment but it's incomplete for now)


## Prerequisite
- have the ansible-vault passwod file
- have access to all or the required ansible role on the git repository
- have access to the ssh key file for the environment in question.(No production ssh is ever shared as its' through AWX as much as possible). This is only required when configuring EC2 instances such as proxy or database boxes.
- install python. Preferably though pyenv in order to freely switch version
- install pyenv-virtualenv to help create python virtual envs to your machine to test different versions of python
- Make sure there is pip package manager
- install using pip
  - ansible-core
  - boto
  - boto3
  - awscli

```shell
$ python --version
  Python 3.8.12 (9ef55f6fc369, Oct 25 2021, 05:10:01)
  [PyPy 7.3.7 with GCC Apple LLVM 13.0.0 (clang-1300.0.29.3)]

$ pyenv versions
  system
  3.10.2
  3.8.12
  dev-pypy-3.8
* pypy3.8-7.3.7 (set by /Users/joseph/.pyenv/version)
  pypy3.8-7.3.7/envs/dev-pypy-3.8

$ pip install ansible-core==2.12.2 boto3 boto awscli

$ pip freeze | grep -e ansible-core -e boto3 -e boto -e awscli
  ansible-core==2.12.2
  awscli==1.22.55
  boto==2.49.0
  boto3==1.21.0
  botocore==1.24.0

```

## How to run a playbook

- After checking out the code from the git repository
- create top level folder localrepo/main/billbox/configuration
- while at the top level of the project run the following

```shell
$ ansible-galaxy role install -r roles/requirements.yml
$ ansible-galaxy collection install -r roles/requirements.yml
```

Once those are done you can run a playbook with the following command:

#### RUN playbook on EC2 instances

```shell
AWS_PROFILE=<awscli_profile_name> ansible-playbook -i ~/path/to/project/projectname/inventory -u ubuntu --private-key ~/path/to/sshkeyfile/folder/billbox/GH/GHBillboxUATOps.pem ~/Dreamoval/Engineering/infrastructure_as_code/ansible_projects/projectname/all_playbook.yml --vault-password-file ~/path/to/vault/passwodfile/projectname/uat/vault.password  -e "global_var_environment=uat" --skip-tags facts
```

#### RUN playbook about containers only

```shell
AWS_PROFILE=<awscli_profile_name> ansible-playbook -i ~/path/to/project/projectname/inventory ~/Dreamoval/Engineering/infrastructure_as_code/ansible_projects/projectname/all_playbook.yml --vault-password-file ~/path/to/vault/passwodfile/projectname/uat/vault.password  -e "global_var_environment=uat" --skip-tags facts
```

| command components | descritpion| example|
|:-------------------|:-----------|:-------|
|AWS_PROFILE| the profile name in your aws configuration| slydepay or billbox
| ansible-playbook | ansible command that executes playbooks | n/a|
| -i /path/../inventory | the -i switch represents the inventory to use for the execution| a folder or a yaml file |
| -u ubuntu| the user to run the execution with if it's about ssh connection | ec2-user or iddi |
| --private-key /path/../ | Specify where to find the ssh pem file for the ssh connection if any| n/a |
| ~/../all_playbook.yml | the actual playbook to execute | application_core_playbook.yml |
|--vault-password-file .../vault.password | This is the key to decrecpt the ansible vault | n/a|
| -e "global_var_environment=uat" | arguably one of the most critical config for running ansible. It determin which environment the call is for | "global_var_environment=prod" |
| --skip-tags facts | there are tags that are repetitive throughout the execution. This flag skips them for the repetition and executes them just once| n/a |

<br>

## Folder Structure
```
/ansible_project_billbox
    |
    +-- collections
          - amazon
          - community
    |
    +-- files
    |
    +-- inventory
          - group_vars
    |
    +-- inventory_backup
          - group_vars
    |
    +-- playbook_vars
          - prod
          - test
          - uat
    |
    +-- roles
          - elasticbeats
          - mongo_family
          - monitoring_family
          - networking
          - percona_mysql
          - security
          - util
          - webserver_family
    |
    +-- templates
```

## Main Config file
The ansible.cfg is the main configuration file where important ansible settings are defined. These settings depict how ansible should behave when executing the playbooks.

<br>

### Playbook Roles
There are a number of Roles that install and prepare the instances for service deployments. Each role executes a series of tasks that install packages and configure the instances. The roles are listed below with their descriptions.

| role | description |
| :----| :-----------|
| ansible_role_utils | installs base utilities, os packages, role dependency packages, and configures them|
| ansible_role_mongo_family | installs and configures all mongo databases|
| ansible_role_security | sets up inventory security with host authentication, firewall, nginx and hardens the inventory OS |
| java_family | installs and configures java requirements on the inventory|
| ansible_role_networking | sets up inventory's networking (Ip tables, proxy and os level firewall)|
| ansible_role_percona_mysql | installs and configures other database servers with percona mysql|
| ansible_role_monitoring_family | installs and configures datadog and insightOps monitoring agents either on the ec2 instances or as sidecars to ecs containers|
| ansible_role_webserver_family | installs webserver packages and configures  webservers on hosts|
| ansible_role_elasticbeats | installs and configures elasticbeats for data transfer|
| collections | downloads and installs collections from the ansible galaxy repository|

<br>

### Playbook Variables
All playbooks make heavy use of variables. Each service playbook has a dedicated variable file where all required variables are defined. Playbook variables documentation can be found [here](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#playbook-variables-documentation).

### Playbook Inventory
The inventory specifies the target hosts that ansible connects to. The inventory group vars also specify ssh arguments for the hosts.

<br>

### EC2 and RDS inventory
  * The bb.aws_ec2.yml and bb.aws_rds.yml files are the main inventory files for all ec2 and rds instances. They define:
    * How we use the **amazon.aws.aws_ec2** plugin to get an inventory of all ec2 and rds instances.
    * The AWS_Profile name we use to connect to AWS services.
    * The regions where the ec2 and rds instances were created.
    * The tags and group names used on the ec2 and rds instances for easy identification.
    * The hostnames and ip_addresses (puplic and private) of all ec2 instances.
    * Databse clusters for rds instances.

<br>

### Inventory Backup.
* A template EC2 inventory script is kept in the inventory_backup directory.
* It is meant to be a backup inventory script that would retrieve information about the ec2 instances.

<br>

## Playbooks
Each billbox microservice has a dedicated playbook that defines a series of actions to deploy or redeploy containers or EC2 instances. All playbooks follow an order for consistency and easy readability. The various sections of the billbox microservice playbooks are detailed below.

## Billbox Microservice Playbooks
|  Playbook | description |
| :---------| :-----------|
| all_playbook| master playbook that executes all other playbooks |
| application_cardhandler_server_playbook| Creates or updates the cardhandler microservice application. The cardhandler processes all card payments. VISA,MASTERCARD, etc..|
| application_config_server_playbook| Creates or updates the config server application. The config server is a unified place where all properties and configurations are kept. Microservices pull their configurations and properties from the config server whenever a deployment is made.|
| application_core_playbook| Creates or updates the main Billbox Core application. Billbox core is the main application that processes transactions. All other applications like the WebPos and the PosAPI connect to the Billbox Core via an API.|
| application_guinea_marketplace_playbook| Creates or updates the Billbox-Guinea marketplace application|
| application_keycloak_server| Creates or updates the keycloak application to manage microservice identity and access|
| application_marketplace_playbook| Creates or updates the Billbox marketplace application|
| application_messenger_server_playbook| Creates or updates the Billbox messenger application. Billbox messenger service, when called, creates a message body that would be sent to end users through the notification server|
| application_metabase_server_playbook| Creates or updates the metabase application. Metabase querries the mongo and mysql databases and provides insight on collected data|
| application_notification_server_playbook| Creates or updates the Notification application. Notification server sends push notifications, emails, sms, etc.. to users|
| application_PosAPI_server| Creates or updates the Billbox PosAPI application. PosAPI creates an invoice for POS devices when called.|
| application_scheduler_server| Creates or updates the scheduler applcation server. The scheduler runs scheduled tasks and cron jobs like settlements aginst hosts and other microservices|
| application_secure_cardhandler_playbook| Creates or updates the secure cardhandler application. The cardhandler application makes calls to the secure cardhandler to processes card payments securely.|
| application_templateengine| Creates or updates the Billbox templateengine. Template Engine is used to generate templates for invoices, messages, notifications and other configurations|
| application_ussd_server_playbook| Creates or updates the Billbox USSD application.|
| application_webpos_playbook| Creates or updates the Billbox WebPOS application. The WebPOS is an web-based invoicing application used to make payments|
| application_zw_marketplace| Creates or updates the Billbox marketplace for Zimbabwe|
| aws_components_setup_playbook| Creates or updates aws infrastructure components such as subnet groups, elasticache and parameter groups before services or applications are deployed |
| aws_securitygroups_playbook| Creates or updates security groups of microservices services.|
| base_infra_setup_playbook| Creates or updates the base infrastructure for the all microservices|
| cardhandler_percona_xtradb_cluster_health_playbook| playbook to check percona database cluster health|
| createnew_or_update_mongo_databases_playbook| Creates or updates existing mongo databases.|
| createnew_or_update_mongo_users_playbook| Creates or updates existing mongo database users|
| createnew_or_update_mysql_databases_playbook| Creates or updates existing mysql databases|
| createnew_or_update_mysql_script_playbook| Creates new or updates existing mysql scripts|
| createnew_or_update_mysql_user_playbook| Creates new or updates existing mysql users|
| fact_gatherer_playbook| playbook to gather important facts about all billbox infrastructure from AWS |
| mongo_cluster_installation| playbook to install mongo cluster for UAT or production|
| mysql_cluster_installation_playbook| installs or updates mysql clusters for UAT or production|
| proxy_alb_forward_gh_zeepay_momo_playbook| playbook to create or update loadbalancer target group and assign the zeepaymomo proxy to it.|
| proxy_playbook| playbook to setup the proxy instance to host proxy connections|
| task_definition_to_docker_compose| playbook to define the task definitions of keycloak proxy, keycloak server, securecore server and securecore proxy as docker containers|
| test_playbook| test playbook to test the services|

<br><br>

## Playbook Structure
The playbooks follow a structure of executing tasks. Since the services run as microservices, their underlying infrastructure are quite similar to each other. Thus, the tasks to create them have certain sections in common. The table below is a breakdown of the common and unique sections as well as their descriptions.

### Common Tasks
| Section | Tasks | Description|
| :-------| :-----| :----------|
| Gathering and setting Facts | Extracting ARN from service discovery <br> Obtaining Service facts| Gathers and sets facts about resources.|
| Secrets and Credentials| Creating Parameter Store secrets| Creates and stores service related credentials inside the AWS Parameter Store|
| Sever Task Definition| Creating ECS Cluster <br> Creating **service** task definition <br> Obtaining target group facts <br> Creating or Updating the ECS service| Creates or updates the ECS task definition of the service|
| Loadbalancing| Creating **service** target group <br> Associating target group to a ALB/NLB listener <br> Associating target group to a ALB/NLB listener with awscli| Creates a loadbalancer target group and assigns the service to it|
| Autoscalling | Creating **service** MEM Scalling Policy <br> Creating **service** CPU Scalling Policy| Creates autoscalling policies for the service|
| Schedule| Creating a Sleep Time scheduled application autoscalling <br> Creating a Sleep Time scheduled application autoscalling with awscli <br> Creating a Wake Time scheduled application autoscalling <br> Creating a Wake Time scheduled application autoscalling with awscli| creates a scheduled sleep and wake up time for the service|



### Unique Tasks
| Section | Task | Description |
| :-------| :----| :-----------|
| Gathering and setting facts| Setting arn of the **service** server ecs service| Obtains the ARN of the server and sets it as a fact to be referenced <br> Obtaining SSL target group facts <br> Obtaining HTTP target group facts.|
| Git Configuration | Clearing Checking Folder <br> Creating billbox configuration git directory <br> Checking out the properties files <br> Staging git changes <br> Committing git repository <br> Pushing **s** changes to remote| Stages and comits changes to Git|
| Database Security | Encryption **server** Mysql Jdbc Username <br> Encryption **server** Mysql Jdbc Password <br> Encryption **server** Mysql Jdbc uri <br> Encryption **server** Mongo dbname <br> Encryption **server** Mongo Username <br> Encryption **server** Mongo Password <br> Encryption **server** MongoDB URI <br> Setting Encrypted **server** credential facts| Encrypts database credentials and URL|
| Server and Database Configuration| Creating **server** config file <br> Creating **server** mysql config file <br> Creating **server** mongo config file| configures both server and databases|





## **First Time Setup**
To successfully configure ansible and run the script on your computer for the first time, follow the laid down steps below;
### Git Configuration ###

```
$ git config --global user.name "<git_username>"
$ git config --global user.email "<your_email>"
$ git config --global core.editor "<preferred_code_editor>"
```
### AWS CLI Setup
```
$ aws configure
### setup credentials for other aws account profiles by editing the aws credentials file.
$ vi ~./aws/credentials
```

### Sdkman Setup
```
### Download and install SDKMan and do the following;
$ sdk list java
$ sdk install <java_version>
$ sdk install gradle
$ sdk install maven
$ sdk install springboot
```

### Ansible Setup
```
  ### Set ANSIBLE_HOME ###
$ export DO_ANSIBLE_HOME=~/<path/to/ansible/home>

  ### Run ansible script test
$ AWS_PROFILE=<your_aws_profile> aws ec2 describe-instances --region eu-west-1
```

**Once the script test is succesful, your local machine is ready to deploy and redeploy new or existing containers unto billbox**
###

## Proxy_Forward_Gh_AfrxprssGlo variables
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_afrxprssvodafone_vhost_file | variable definitions to setup virtual host configuration|
| Logging | proxy_forward_gh_afrxprssvodafone_log_access_file <br> proxy_forward_gh_afrxprssvodafone_log_error_file | variable definitions to configure access and error logs location|
| Proxy Upstream | proxy_forward_gh_afrxprssvodafone_upstream_host1 <br> proxy_forward_gh_afrxprssvodafone_upstream_host1_mon_type <br> proxy_forward_gh_afrxprssvodafone_upstream_host1_mon_scheme| variable definitions to configure data upstream for the proxy host|
| Enabling roles and installing packages | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details| variable definitions to enable webserver roles and to install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to configure nginx webserver |
| Elasticbeats Setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats|
| Monitoring | monitoringfamily_r7insightops_forward_gh_afrxprssvodafone_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_afrxprssvodafone_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to setup and configure rapid7insightOps agent to monitor the proxy connection|

<br>

## Proxy_Forward_Gh_AirtelTigoBankIntegrationn variables
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_airteltigobankintegration_vhost_file | variable definitions to setup virtual host configuration|
| Logging| proxy_forward_gh_airteltigobankintegration_log_access_file <br> proxy_forward_gh_airteltigobankintegration_log_error_file| variable definitions to configure access and error logs location|
| Proxy upstream | proxy_forward_gh_airteltigobankintegration_upstream_host1 <br> proxy_forward_gh_airteltigobankintegration_upstream_host1_mon_type <br> proxy_forward_gh_airteltigobankintegration_upstream_host1_mon_scheme| variable definitions to configure proxy data upstream|
| Enabling webserver roles and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details| variable definitions to enable the webserver role and to install nginx packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to configure the nginx webserver|
| Elasticbeats setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats|
| Monitoring| monitoringfamily_r7insightops_forward_gh_airteltigobankintegration_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_airteltigobankintegration_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightops agent to monitor the proxy connection|

<br>

## Proxy_Forward_Gh_AppsnmobAirtelTigo variables
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_appsnmobaiterltigo_vhost_file | variable definitions to setup virtual host configuration|
| Logging | proxy_forward_gh_appsnmobaiterltigo_log_access_file <br> proxy_forward_gh_appsnmobaiterltigo_log_error_file| variable definitions to configure access and error logs location|
| Proxy upstream | forward_gh_appsnmobaiterltigo_upstream_host1 <br> forward_gh_appsnmobaiterltigo_upstream_host1_mon_type <br> forward_gh_appsnmobaiterltigo_upstream_host1_mon_scheme | variable definitions to configure proxy data upstream|
| Enabling webserver role and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details| variable definitions to enable webserver roles and to install packages|
| Webserver configuration | webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to configure the nginx webserver|
| Elasticbeats setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats to ship data|
| Monitoring | monitoringfamily_r7insightops_forward_gh_appsnmobaiterltigo_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_appsnmobaiterltigo_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps agent to monitor the connection|

<br>

## Proxy_Forward_Gh_Ghipss variables
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_ghipss_vhost_file | virtual host configuration file definition|
| Logging | proxy_forward_gh_ghipss_log_access_file <br> proxy_forward_gh_ghipss_log_error_file | host's log file variable definition|
| Proxy Upstream | proxy_forward_gh_ghipss_upstream_host1 <br> proxy_forward_gh_ghipss_upstream_host1_mon_type <br> proxy_forward_gh_ghipss_upstream_host1_mon_scheme| proxy data upstream variable definition|
| SSL | proxy_forward_gh_ghipss_ssl_cert <br> proxy_forward_gh_ghipss_ssl_key <br> proxy_forward_gh_ghipss_ssl_folder_path| ssl variable definitions |
| Filesystem | util_filesystem_enable <br> util_filesystem_create_directory_with_pem_details_dict| filesystem setup variable definitions|
| Enabling and installing packages | aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable| variable definitions to enable and install required packages|
|S3| aws_s3_enable <br> aws_s3_pull_object_details| variables definitions for ssl file storage in Amazon S3|
| Webserver configuration| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to configure the proxy webserver|
| Elasticbeats setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to setup elasticbeats to ship collected data|
| Monitoring | monitoringfamily_r7insightops_forward_gh_ghipss_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_ghipss_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps agent to monitor the proxy webserver|

<br>

## Proxy_Forward_Gh_Gwcl variables
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_gwcl_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_gh_gwcl_log_access_file <br> proxy_forward_gh_gwcl_log_error_file| virtual host's log file variable definition|
| Proxy Upstream| proxy_forward_gh_gwcl_upstream_host1 <br> proxy_forward_gh_gwcl_upstream_host1_mon_type <br> proxy_forward_gh_gwcl_upstream_host1_mon_scheme| proxy data upstream variable definition|
| Enabling Webserver roles and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to enable webserver roles and install packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variable definitions to configure the proxy webserver|
| Elasticbeats setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats|
| Monitoring | monitoringfamily_r7insightops_forward_gh_gwcl_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_gwcl_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps to collect logs from the proxy host|

<br><br>
## **Deploying or Redeploying existing and new containers to a billbox service**
Deployments are done based on deployment requests. The request would contain the name of the service, environment, new service version, and property changes (if any).
There are two ways to deploy to a billbox service.
* Deploying using AWX (Used when there are no property changes to the deployment)
* Deploying using the Billbox Ansible script (Used when there are property changes)

### Deploying with AWX (No property changes)
* AWX is rather the recommended way to deploy to a Billbox service when there are no property changes to be made. We have configured AWX to pull from the **Develop** branch of this project making little or no room for errors when deploying to a service.

### Deploying with the Billbox Ansible script (With property changes)
* Deploying from the script is done when property changes are to be made to a service or it's container. Do the following when deploying to a service that requires a property change.
  * Login to TeamCity and confirm the build to be deployed.
  * With your IDE, pull from the git repository to update your code.
  * Locate the property file of the service in the templates directory and update it with the new values. (Properties for the core server are defined in its variable file)
  * Update the image of the service in the global_vars file to match the build's tag in TeamCity.
  * Uncomment the service's playbook in the all_playbook.yml file and save changes. Comment other service playbooks.
  * Run the all_playbook.yml file to start the deployment.

<br>




## Troubleshooting on your first set up.
Although this documentation covers the pre-requisites and everything you need to run the project, you might encounter some challenges ranging from a missing library or a broken package. This section covers some of the common issues you might encounter while setting up your device and how to resolve them.


### GitLab Access Error
Error sample:
```
\nfatal: unable to access 'https://bitbucket.org/kowri/kowribusinessconfigs.git': The requested URL returned error: 400\n"
```
Reason: User not granted access to git repository. To resolve, request for gitlab access credentials.

### Issues installing Spring Cloud on SpringBoot CLI
Error sample:
```
"stderr": "/bin/sh: 1: spring: not found", "stderr_lines": ["/bin/sh: 1: spring: not found"]
```
**Reason**: This usually happens when springboot is not installed or setup on the device. To resolve,
* Open your terminal and follow the steps below;
```
$ apt-get update
$ apt-get upgrade
$ apt-get install unzip zip openjdk-11-jdk ( You can use the latest stable version of jdk)
```
* Open your **~/.bashrc** file and add the command below to the last line of the file and save the new changes.
```
export JAVA_HOME="/usr/lib/jvm/java-1.11.0-openjdk-amd64"
```
* Visit "https://get.sdkman.io" to download and install SdkMan from the official website.
* In your terminal, run
```
$ sdk install maven
$ sdk install springboot 2.3.6.RELEASE
$ sdk use springboot 2.3.6.RELEASE
$ spring install org.springframework.cloud:spring-cloud-cli:2.1.0.RELEASE
```
Once the steps have been executed and all dependencies have been resolved, the playbooks should run just fine.



### /files Directory
This directory contains additional condition files for the various application load balancers and their execution environments as well as the SQL script for quartz_scheduler_db.

### The Execution Process.
Once the deployment environment is ready and all dependencies/ requirements are met, the application can be fully deployed without issues. Thus said, the deployment follows a procedure to execute. These are structured processes to ensure that playbooks that depend on the completion of others are not run first.



