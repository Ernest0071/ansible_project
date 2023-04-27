# Playbook Variables Documentation
This documentation captures the variables defined and used in the main playbooks. All variables defined and used in the project have been documented here.
<br>

<br>

| Index|    |
| :----| :--|
| Application Server variables | [Global Variables](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#global-variables) \| [Cardhandler server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#cardhandler-server-variables) \| [SecureCardHandler](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#securecardhandler-variables)\| [Config server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#config-server-variables) \| [Application Core](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#application-core-variables) \| [Keycloak application](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#keycloak-application-variables)\| <br> [Marketplace application](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#marketplace-application-variables) \| [ZW_Marketplace](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#zw_marketplace-variables) \| [Messenger application](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#messenger-application-variables) \| [Metabase application](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#metabase-application-variables) \| [Notification server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#notification-server-variables) \| [PosAPI server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#posapi-server-variables) \| <br> [Scheduler server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#scheduler-server-variables) \| [Secure Core server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#secure-core-server-variables) \| [Template Engine server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#template-engine-server-variables) \| [USSD server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ussd-server-variables)\| [WebPos server](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#webpos-server-variables) \| [Guinea_marketplace](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#guinea_marketplace-variables) \| <br>
| Database Variables| [Mongo Databases](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#mongo-database-server-variables) \| [MySQL Database](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#mysql-database-server-variables) \| [Users_Mongo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#users_mongo-variables) \| [Mongo_arbiter](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#mongo_arbiter-variables) \| [Mongo database](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#mongo-database-variables) \| <br> [Percona MySQL database](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#mysql-database-variables) \| [Script_Mysql variables](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#script_mysql-variables) \|
| Proxy Variables| [Proxy_Default](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_default-variables) \| [GhafricXpressGlo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghafricxpressglo-proxy-variables) \| [GhAirTigoBankInt](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghairtigobankint-proxy-variables) \| [Ghgwcl](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghgwcl-proxy-variables) \| [GhMTNOva](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghmtnova-proxy-variables) \| [Ghria](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghria-proxy-variables) \| [Ghstanlib](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghstanlib-proxy-variables) \| [Ghsurfline](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghsurfline-proxy-variables) \| <br> [Ghtotal](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#ghtotal-proxy-variables) \|  [Proxy_Forward_Gh_AfrxprssAirteltigo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_afrxprssairteltigo-variables) \| [Proxy_Forward_Gh_AfrxprssGlo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_afrxprssglo-variables) \| [Proxy_Forward_Gh_AfrxprssGlo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_afrxprssglo-variables-1) \| <br> [Proxy_Forward_Gh_AirtelTigoBankIntegration](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_airteltigobankintegrationn-variables) \| [Proxy_Forward_Gh_AppsnmobAirtelTigo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_appsnmobairteltigo-variables) \| [Proxy_Forward_Gh_Ghipss](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_ghipss-variables) \| <br> [Proxy_Forward_Gh_Gwcl variables](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_gwcl-variables) \| [Proxy_Forward_Gh_MtnAirtime](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_mtnairtime-variables) \| [Proxy_Forward_Gh_MtnDataBundle](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_mtndatabundle-variables) \| [ZwStanbic](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#zwstanbic-proxy-variables) \| [ZwCellulant](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#zwcellulant-proxy-variables) \| <br>  [Proxy_Forward_Gh_MtnFttxBundle](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_mtnfttxbundle-variables) \| [Proxy_Forward_Gh_StanbicDataPower](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_stanbicdatapower-variables) \| [Proxy_Forward_Gh_VodafoneCash](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_vodafonecash-variables) \| <br> [Proxy_Forward_Gh_ZeePayMomo](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_gh_zeepaymomo-variables) \| [Proxy_Forward_ZW_Ecocash](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_zw_ecocash-variables) \| [Proxy_Forward_ZW_Econet variables](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_forward_zw_econet-variables) \| <br> [Proxy_Reverse_ZW_Econet](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#proxy_reverse_zw_econet-variables) \|
| Monitoring Agent Variables| [Monitoring_InsightOps](https://github.com/DreamOval/ansible_project_billbox/tree/develop/playbook_vars#monitoring_insightops-variables) \|

<br><br>
## **Global Variables**
| Global variable section | description |
| :-----------------------| :-----------|
| Elasticache section| defines the replication group name, version used, port, number and type of instance for the elasticache redis service|
| Kafka Section | defines cluster name, instance type, ports and the number of nodes required for the Kafka service|
| Elasticsearch (ELK) Section | defines the name, version, instance type and conditions for the elasticsearch instance |
| Proxy Section | defines connection ports for proxy instances, nginx proxies, and paths to ssl keys stored in S3 buckets.|
| Networking Section | defines region variables for EC2 and RDS instances, VPC CIDRs, security groups for services and subnets for EC2 and RDS instances |
| Mysql section | defines variables for MySQL and RDS connection port as well as MySQL and RDS target database names.|
| Mongo Section | defines variables for mongo database connection port, config files and directory paths, s3 object details and mongo db release versions. |
| Container Section | defines variables for container names, images, host and container ports, domain and loadbalancer priority level for all containerized servers.|

<br>

### **Cardhandler server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_cardhandler_server_enabled | enables the cardhandler service task.|
| Region setup | smartgrid_active_region | defines the region of the task |
| Namespace setup | smartgrid_active_priv_dns_namespace | defines a private namespace for cardhandler server's dns |
| ECS task definition | bb_cardhandler_server_task_family_name <br> bb_cardhandler_server_task_executionRoleArn <br> bb_cardhandler_server_task_networkmode <br> bb_cardhandler_server_task_ecsmode <br> bb_cardhandler_server_task_cpu <br> bb_cardhandler_server_task_memory <br> bb_cardhandler_server_task_container_name <br> bb_cardhandler_server_task_container_image <br> bb_cardhandler_server_task_container_cpu <br> bb_cardhandler_server_task_container_memory <br> bb_cardhandler_server_task_container_memoryReservation <br> bb_cardhandler_server_task_container_credentials_parameter <br> bb_cardhandler_sidecar_server_task_container_credentials_parameter <br> bb_cardhandler_server_task_container_credentials_parameter <br> bb_cardhandler_server_task_container_essential <br> bb_cardhandler_sidecar_server_task_container_essential <br> bb_cardhandler_server_task_container_java_vars | Cardhandler's container and application properties definition |
| Envrionment | bb_cardhandler_server_task_container_mon_env <br> bb_cardhandler_server_task_container_env <br> bb_cardhandler_server_task_container_secret_rawenv <br> bb_cardhandler_server_task_container_mon_secretenv <br> bb_cardhandler_server_task_container_secretenv <br> bb_cardhandler_nginx_server_task_container_env | environmental variable definitions for cardhandler task and task secret |
| Logging | bb_cardhandler_server_task_container_log_driver <br> b_cardhandler_server_task_container_log_logsgroup <br> bb_cardhandler_server_task_container_log_logsregion <br> bb_cardhandler_server_task_container_log_logsprefix | variable definitions for collecting container logs|
| Service name | bb_cardhandler_service_name | cardhandler service name definition|
| Server loadbalancing | bb_cardhandler_alb_arn <br> bb_cardhandler_targetgroup_name <br> bb_cardhandler_targetgroup_protocol <br> bb_cardhandler_targetgroup_success_http_code <br> bb_cardhandler_targetgroup_hc_interval <br> bb_cardhandler_targetgroup_hc_timeout <br> bb_cardhandler_targetgroup_hc_healthycount <br> bb_cardhandler_targetgroup_hc_unhealthycount <br> bb_cardhandler_targetgroup_hc_path <br> bb_cardhandler_targetgroup_hc_protocol <br> bb_cardhandler_targetgroup_targettype | variables to attach the cardhandler server to a loadbalancer|
| Autoscalling | bb_cardhandler_service_count <br> bb_cardhandler_service_platform_version <br> bb_cardhandler_service_hc_graceperiod <br> bb_cardhandler_service_autoscalling_policy_type <br> bb_cardhandler_service_autoscalling_min_task <br> bb_cardhandler_service_autoscalling_max_task <br> bb_cardhandler_service_mem_autoscalling_policy_name <br> bb_cardhandler_service_cpu_autoscalling_policy_name <br> bb_cardhandler_service_mem_autoscalling_tracking_scaling_target_value <br> bb_cardhandler_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_cardhandler_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_cardhandler_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_cardhandler_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_cardhandler_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_cardhandler_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_cardhandler_service_scheduled_autoscalling <br> bb_cardhandler_service_cpu_autoscalling_tracking_scalin_cooldown | autoscalling variable definitions for the cardhandler service.|
| Schedule | bb_cardhandler_service_wake_cron <br> bb_cardhandler_service_sleep_cron | variable definitions for UAT server's sleep & wake up time|
| Monitoring | bb_cardhandler_server_task_container_datadog_essential <br> bb_cardhandler_server_task_container_envoy_essential | variables definitions for server's monitoring agents|
| URLs | bb_cardhandler_transaction_url_success <br> bb_cardhandler_transaction_url_error | success and error url domain definitions |
| Redis | bb_cardhandler_redis_host <br> bb_cardhandler_redis_port | variable definitions for elasticache redis |
| Processing | bb_cardhandler_procesor | variable definition for card processing gateway |
| Ip Address | bb_cardhandler_service_assign_public_ip | public IP assignment variable definition|
| Cluster | bb_cardhandler_elk_cluster_nodes | elasticache cluster nodes definition |
| Paths| bb_cardhandler_context_path | cardhandler context path definition |

<br>

## **Config server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_config_server_enabled | enables the config server task|
| Region setup | bb_active_region | defines the region of the config server task |
| Namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the config server's dns |
| ECS task definition | bb_config_server_task_family_name <br> bb_config_server_task_executionRoleArn <br> bb_config_server_task_networkmode <br> bb_config_server_task_ecsmode <br> bb_config_server_task_cpu <br> bb_config_server_task_memory <br> bb_config_server_task_container_name <br> bb_config_server_task_container_image <br> bb_config_server_task_container_cpu <br> bb_config_server_task_container_memory <br> bb_config_server_task_container_memoryReservation <br> bb_config_server_task_container_credentials_parameter <br> bb_config_server_task_container_essential <br> bb_config_server_task_container_java_vars | Config server's container task  definition. This section defines the contaner's name, image, networkmode, allocated and reserved memory, properties, and java variables |
| Envrionment definition | bb_config_server_task_container_secretenv_definition <br> bb_config_server_task_container_secretenv <br> bb_config_server_task_container_env <br> bb_config_server_datadog_task_container_env | Defines environment variables for config server container |
| Logging | bb_config_server_task_container_log_driver <br> bb_config_server_task_container_log_logsgroup <br> bb_config_server_task_container_log_logsregion <br> bb_config_server_task_container_log_logsprefix | variable definition for container logs collection|
| Service name | bb_config_service_name | config server name |
| Loadbalancing | bb_config_targetgroup_name <br> bb_config_targetgroup_protocol <br> bb_config_targetgroup_success_http_code <br> bb_config_targetgroup_hc_interval <br> bb_config_targetgroup_hc_timeout <br> bb_config_targetgroup_hc_healthycount <br> bb_config_targetgroup_hc_unhealthycount <br> bb_config_targetgroup_hc_path <br> bb_config_targetgroup_hc_protocol <br> bb_config_targetgroup_targettype <br> bb_config_alb_arn <br> bb_config_s÷ervice_hc_graceperiod | variable definitions to assign the config server to a loadbalancer target group and configure health checks |
| Schedule | bb_config_service_wake_cron <br> bb_config_service_sleep_cron | variable definitions for  UAT. defines sleep & wake up time|
| Essential | bb_config_service_awscli_enabled | Enabling AWS CLI for the config server |
| Versions | bb_config_service_platform_version <br> bb_config_service_count  | sets the platform version and service count of the config server|

<br>

## **Application Core variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Application ports | bb_core_main_port <br> bb_core_int_port <br> bb_core_tomcat_jmx_port | ports definition for billbox application's internal and external connections.|
| Enabling service | bb_core_server_enabled | variable definitions for the server's active state.|
| Region setup | bb_active_region | defines the region of the billbox core server |
| Namespace setup | bb_active_priv_dns_namespace | defines a private namespace for core server's dns |
| ECS task definition | bb_core_server_task_family_name <br> bb_core_server_task_networkmode <br> bb_core_server_task_executionRoleArn <br> bb_core_server_task_ecsmode <br> bb_core_server_task_cpu <br> bb_core_server_task_memory <br> bb_core_server_task_container_name <br> bb_core_server_task_container_image <br> bb_core_server_task_container_cpu <br> bb_core_server_task_container_memory <br> bb_core_server_task_container_memoryReservation | Billbox core's container properties definition.|
| Credentials | bb_core_server_task_container_credentials_parameter <br> bb_core_server_task_container_credentials_parameter | billlbox core container secrets definition|
| Container ports | bb_core_server_task_container_portmap_containerport <br> bb_core_server_task_container_portmap_hostport | port definitions for billbox core container and host |
|Esssential | bb_core_server_task_container_essential <br> bb_core_sidecar_server_task_container_essential | variable definitions to set container and it's side car as important in the cluster |
| Paths | bb_core_image_path <br> bb_core_download_path | billbox core cointainer image and download path definition|
| Properties | bb_core_server_owasp_resc <br> bb_core_server_auth_cache_ttl_mins <br> bb_core_server_max_login_attempt <br> bb_core_server_max_use_forward_headers | properties definition for billbox core application.|
| Application properties  | bb_core_server_task_container_java_vars | java properties definition for billbox core application |
| Environment | bb_core_server_task_container_secretenv_definition <br> bb_core_server_task_container_secretenv <br> bb_corenginx_server_task_container_env <br> bb_core_server_task_container_env <br> bb_core_server_task_container_mon_env_docker_env_tags <br> bb_core_server_task_container_mon_env <br> bb_core_server_task_container_log_env <br> bb_core_server_task_container_mon_secretenv | Environmental variable definitions for billbox core task |
|Logging | bb_core_server_task_container_log_driver <br> bb_core_server_task_container_log_logsgroup <br> bb_core_server_task_container_log_logsregion <br> bb_core_server_task_container_log_logsprefix | variable definitions for collecting container logs |
| Loadbalancing | bb_core_alb_arn <br> bb_core_service_name <br> bb_core_targetgroup_name <br> bb_core_targetgroup_protocol <br> bb_core_ssl_targetgroup_name <br> bb_core_ssl_targetgroup_protocol <br> bb_core_targetgroup_success_http_code <br> bb_core_targetgroup_hc_interval <br> bb_core_targetgroup_hc_timeout <br> bb_core_targetgroup_hc_healthycount <br> bb_core_targetgroup_hc_unhealthycount <br> bb_core_targetgroup_hc_path <br> bb_core_targetgroup_hc_protocol <br> bb_core_ssl_targetgroup_hc_protocol <br> bb_core_targetgroup_targettype | variable definitions to assign billbox core server to a loadbalancer target group and configure health checks  |
| Service versioning | bb_core_service_count <br> bb_core_service_platform_version <br> bb_core_service_hc_graceperiod | defines the verion of the billbox service platform |
| Autoscalling | bb_core_service_autoscalling_policy_type <br> bb_core_service_autoscalling_min_task <br> bb_core_service_autoscalling_max_task <br> bb_core_service_mem_autoscalling_policy_name <br> bb_core_service_cpu_autoscalling_policy_name <br> bb_core_service_mem_autoscalling_tracking_scaling_target_value <br> bb_core_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_core_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_core_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_core_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_core_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_core_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_core_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_core_service_scheduled_autoscalling | autoscalling variable definitions for billbox core's server |
| UUtility | bb_core_service_awscli_enabled | enabling AWS CLI on the server|
| Schedule | bb_core_service_sleep_cron <br> bb_core_service_wake_cron | variable definitions for UAT server's sleep & wake up time|

<br>

## **Keycloak application variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_keycloak_server_enabled | enables the keycloak application server.|
| Region setup | smartgrid_active_region | defines the region of the keycloak server task|
| Namespace setup | smartgrid_active_priv_dns_namespace | defines a private namespace for keycloack server's dns |
| ECS task definition | bb_keycloak_server_task_family_name <br> bb_keycloak_server_task_executionRoleArn <br> bb_keycloak_server_task_networkmode <br> bb_keycloak_server_task_ecsmode <br> bb_keycloak_server_task_cpu <br> bb_keycloak_server_task_memory <br> bb_keycloak_server_task_container_name <br> bb_keycloak_server_task_container_image <br> bb_keycloak_server_task_container_cpu <br> bb_keycloak_server_task_container_memory <br> bb_keycloak_server_task_container_memoryReservation <br> bb_keycloak_server_task_force_create | keycloak application container properties definition.|
| Credentials | bb_keycloak_server_task_container_credentials_parameter | defines authentication secrets for connecting with dockerhub|
| Essential | bb_keycloak_server_task_container_essential <br> bb_keycloak_sidecar_server_task_container_essential | variable definitions to set container and it's side car as important in the cluster|
| Application properties | bb_keycloak_server_task_container_java_vars | Java propertiey variables for the keycloak application |
| Environment | bb_keycloak_server_task_container_mon_env <br> bb_keycloak_server_task_container_env <br> bb_keycloak_server_task_container_secret_rawenv <br> bb_keycloak_server_task_container_mon_secretenv <br> bb_keycloak_server_task_container_secretenv <br> bb_keycloak_nginx_server_task_container_env | environmental variable definitions for the container and it's connection secrets |
| Logging | bb_keycloak_server_task_container_log_driver <br> bb_keycloak_server_task_container_log_logsgroup <br> bb_keycloak_server_task_container_log_logsregion <br> bb_keycloak_server_task_container_log_logsprefix | variable definition for collecting the server's logs |
| Loadbalancing | bb_keycloak_alb_arn <br> bb_keycloak_service_name <br> bb_keycloak_targetgroup_name <br> bb_keycloak_targetgroup_protocol <br> bb_keycloak_targetgroup_success_http_code <br> bb_keycloak_targetgroup_hc_interval <br> bb_keycloak_targetgroup_hc_timeout <br> bb_keycloak_targetgroup_hc_healthycount <br> bb_keycloak_targetgroup_hc_unhealthycount <br> bb_keycloak_targetgroup_hc_path <br> bb_keycloak_targetgroup_hc_protocol <br> bb_keycloak_targetgroup_hc_port <br> bb_keycloak_targetgroup_targettype | variable definitions to assign keycloack server to a loadbalancer target group and configure health checks.|
| Autoscalling | bb_keycloak_service_count <br> bb_keycloak_service_platform_version <br> bb_keycloak_service_hc_graceperiod <br> bb_keycloak_service_autoscalling_policy_type <br> bb_keycloak_service_autoscalling_min_task <br> bb_keycloak_service_autoscalling_max_task <br> bb_keycloak_service_mem_autoscalling_policy_name <br> bb_keycloak_service_cpu_autoscalling_policy_name <br> bb_keycloak_service_mem_autoscalling_tracking_scaling_target_value <br> bb_keycloak_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_keycloak_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_keycloak_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_keycloak_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_keycloak_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_keycloak_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_keycloak_service_scheduled_autoscalling <br> bb_keycloak_service_cpu_autoscalling_tracking_scalin_cooldown | autoscalling variable definitions for the keycloak server |
| Utility | bb_keycloak_service_awscli_enabled | defines the active state of the AWS CLI on the server |
| Schedule | bb_keycloak_service_wake_cron <br> bb_keycloak_service_sleep_cron | variable definitions for UAT server's sleep & wake up time|
| Proxy | bb_keycloak_proxyserver_listen_port <br> bb_keycloak_proxyserver_name | variable definitions for proxy connections |

<br>

## **Marketplace application variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| ECS task definition | bb_marketplace_server_task_family_name <br> bb_marketplace_server_task_executionRoleArn <br> bb_marketplace_server_task_networkmode <br> bb_marketplace_server_task_ecsmode <br> bb_marketplace_server_task_cpu <br> bb_marketplace_server_task_memory <br> bb_marketplace_server_task_container_name <br> bb_marketplace_server_task_container_image <br> bb_marketplace_server_task_container_cpu <br> bb_marketplace_server_task_container_memory | marketplace container properties definition |
| Secrets and credentials | bb_marketplace_server_task_container_credentials_parameter <br> bb_marketplace_sidecar_server_task_container_credentials_parameter <br> bb_marketplace_server_task_container_credentials_parameter <br> bb_marketplace_sidecar_server_task_container_credentials_parameter <br> bb_marketplace_server_task_container_credentials_parameter | secrets and credentials variable definition for the marketplace |
| Essential | bb_marketplace_server_task_container_essential <br> bb_marketplace_sidecar_server_task_container_essential | variable definitions to set container and it's side car as important in the cluster |
| Environment | bb_marketplace_server_task_container_env <br> bb_marketplacenginx_server_task_container_env <br> bb_marketplace_server_task_container_mon_env <br> bb_marketplace_server_task_container_secretenv_definition <br> bb_marketplace_server_task_container_secretenv | secrets environmental variable definitions for the marketplace container and sidecars |
| Logging | bb_marketplace_server_task_container_log_driver <br> bb_marketplace_server_task_container_log_logsgroup <br> bb_marketplace_server_task_container_log_logsregion <br> bb_marketplace_server_task_container_log_logsprefix | variable definitions to collect logs from the marketplace container |
| Loadbalancing | bb_marketplace_alb_arn | bb_marketplace_service_name | bb_marketplace_targetgroup_name | bb_marketplace_targetgroup_protocol | bb_marketplace_targetgroup_success_http_code | bb_marketplace_targetgroup_hc_interval | bb_marketplace_targetgroup_hc_timeout | bb_marketplace_targetgroup_hc_healthycount <br> bb_marketplace_targetgroup_hc_unhealthycount <br> bb_marketplace_targetgroup_hc_path <br> bb_marketplace_targetgroup_hc_protocol <br> bb_marketplace_targetgroup_targettype | variable definitions to assign the marketplace server to a loadbalancer target group and configure health checks.|
| Autoscalling | bb_marketplace_service_count <br> bb_marketplace_service_platform_version <br> bb_marketplace_service_hc_graceperiod <br> bb_marketplace_service_autoscalling_policy_type <br> bb_marketplace_service_autoscalling_min_task <br> bb_marketplace_service_autoscalling_max_task <br> bb_marketplace_service_mem_autoscalling_policy_name <br> bb_marketplace_service_cpu_autoscalling_policy_name <br> bb_marketplace_service_mem_autoscalling_tracking_scaling_target_value <br> bb_marketplace_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_marketplace_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_marketplace_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_marketplace_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_marketplace_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_marketplace_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_marketplace_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_marketplace_service_scheduled_autoscalling | autoscalling definitions for the marketplace server |
| Utility | bb_marketplace_service_awscli_enabled | AWS CLI state definition |
| Schedule | bb_marketplace_service_wake_cron <br> bb_marketplace_service_sleep_cron | variable definitions for the marketplace UAT server's sleep & wake up time|

<br>

## **Messenger application variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Ports | bb_messenger_main_port <br> bb_messenger_int_port <br> bb_messenger_tomcat_jmx_port | port definitions for internal and external connections |
| Enabling service | bb_messenger_server_enabled | enables the messenger application server.|
| Regions | bb_active_region | messenger server's AWS region definition |
| DNS namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the messenger application's server dns |
| ECS task definition | bb_messenger_server_task_family_name <br> bb_messenger_server_task_networkmode <br> bb_messenger_server_task_executionRoleArn <br> bb_messenger_server_task_ecsmode <br> bb_messenger_server_task_cpu <br> bb_messenger_server_task_memory <br> bb_messenger_server_task_container_name <br> bb_messenger_server_task_container_image <br> bb_messenger_server_task_container_cpu <br> bb_messenger_server_task_container_memory <br> bb_messenger_server_task_container_credentials_parameter | messenger application container properties definition |
| Essential | bb_messenger_server_task_container_essential <br> bb_messenger_sidecar_server_task_container_essential | defines the server container as important in its cluster |
| Environment | bb_messenger_server_task_container_secretenv_definition <br> bb_messenger_server_task_container_mon_secretenv <br> bb_messenger_server_task_container_env <br> bb_messenger_server_task_container_mon_env | environmental variable definitions for the server service's ECS task |
| Logging | bb_messenger_server_task_container_log_driver <br> bb_messenger_server_task_container_log_logsgroup <br> bb_messenger_server_task_container_log_logsregion <br> bb_messenger_server_task_container_log_logsprefix | variable definition for the collection of logs|
| Autoscalling | bb_messenger_alb_arn <br> bb_messenger_service_name <br> bb_messenger_service_scheduled_autoscalling <br> bb_messenger_service_count <br> bb_messenger_service_platform_version <br> bb_messenger_service_autoscalling_policy_type <br> bb_messenger_service_autoscalling_min_task <br> bb_messenger_service_autoscalling_max_task <br> bb_messenger_service_mem_autoscalling_policy_name <br> bb_messenger_service_cpu_autoscalling_policy_name <br> bb_messenger_service_mem_autoscalling_tracking_scaling_target_value <br> bb_messenger_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_messenger_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_messenger_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_messenger_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_messenger_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_messenger_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_messenger_service_cpu_autoscalling_tracking_scalin_cooldown | autoscalling definitions for the messenger application server |
| Utility | bb_messenger_service_awscli_enabled | AWS CLI active state for the server|
| Schedule | bb_messenger_service_wake_cron <br> bb_messenger_service_sleep_cron | variable definitions for the messenger application UAT server's sleep & wake up time|

<br>

## **Metabase application variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| ECS task definition | bb_metabase_server_task_family_name <br> bb_metabase_server_task_executionRoleArn <br> bb_metabase_server_task_networkmode <br> bb_metabase_server_task_ecsmode <br> bb_metabase_server_task_cpu <br> bb_metabase_server_task_memory <br> bb_metabase_server_task_container_name <br> bb_metabase_server_task_container_image <br> bb_metabase_server_task_container_cpu <br> bb_metabase_server_task_container_memory <br> bb_metabase_server_task_container_credentials_parameter <br> bb_metabase_server_is_new_setup <br> bb_metabase_sidecar_server_task_container_credentials_parameter | metabase application container properties definition |
| Essential | bb_metabase_server_task_container_essential <br> bb_metabase_sidecar_server_task_container_essential <br> bb_metabase_server_task_container_java_vars | defines the server container as important in its cluster |
| Environment | bb_metabase_server_task_container_env <br> bb_metabasenginx_server_task_container_env <br> bb_metabase_server_task_container_mon_env <br> bb_metabase_server_task_container_secretenv_definition <br> bb_metabase_server_task_container_secretenv| environmental variable definitions for the server |
| Logging | bb_metabase_server_task_container_log_driver <br> bb_metabase_server_task_container_log_logsgroup <br> bb_metabase_server_task_container_log_logsregion <br> bb_metabase_server_task_container_log_logsprefix | variable definition for the collection of loggs|
| Loadbalancing | bb_metabase_alb_arn <br> bb_metabase_service_name <br> bb_metabase_targetgroup_name <br> bb_metabase_targetgroup_protocol <br> bb_metabase_targetgroup_success_http_code <br> bb_metabase_targetgroup_hc_interval <br> bb_metabase_targetgroup_hc_timeout <br> bb_metabase_targetgroup_hc_healthycount <br> bb_metabase_targetgroup_hc_unhealthycount <br> bb_metabase_targetgroup_hc_path <br> bb_metabase_targetgroup_hc_protocol <br> bb_metabase_targetgroup_targettype <br> bb_metabase_service_count <br> bb_metabase_service_platform_version <br> bb_metabase_service_hc_graceperiod | variable definitions to assign the metabase server to a loadbalancer target group and configure health checks.|
| Autoscalling | bb_metabase_service_autoscalling_policy_type <br> bb_metabase_service_autoscalling_min_task <br> bb_metabase_service_autoscalling_max_task <br> bb_metabase_service_mem_autoscalling_policy_name <br> bb_metabase_service_cpu_autoscalling_policy_name <br> bb_metabase_service_mem_autoscalling_tracking_scaling_target_value <br> bb_metabase_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_metabase_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_metabase_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_metabase_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_metabase_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_metabase_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_metabase_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_metabase_service_scheduled_autoscalling | autoscalling definitions for the metabase server |
| Utility | bb_metabase_service_awscli_enabled | AWS CLI active state for the server|
| Schedule | bb_metabase_service_wake_cron <br> bb_metabase_service_sleep_cron | variable definitions for the metabase UAT server's sleep & wake up time|

<br>

## **Notification server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Ports | bb_notification_main_port <br> bb_notification_int_port <br> bb_lns_configmap_namespace_and_port_for_templateengine <br> bb_lns_kafka_bootstrap <br> bb_lns_configmap_namespace_and_port_for_messenger <br> bb_notification_tomcat_jmx_port | port definitions for internal and external connections |
| Enabling service | bb_notification_server_enabled | enables the notification server.|
| Regions | bb_active_region | notification server's AWS region definition |
| DNS namespace and base url setup | bb_active_priv_dns_namespace <br> bb_notification_service_vars_main_base_url | defines a private namespace and URL for the notification server dns |
| ECS task definition | bb_notification_server_task_family_name <br> bb_notification_server_task_networkmode <br> bb_notification_server_task_executionRoleArn <br> bb_notification_server_task_ecsmode <br> bb_notification_server_task_cpu <br> bb_notification_server_task_memory <br> bb_notification_server_task_container_name <br> bb_notification_server_task_container_image <br> bb_notification_server_task_container_cpu <br> bb_notification_server_task_container_memory <br> bb_notification_server_task_container_memoryReservation <br> bb_notification_server_task_container_credentials_parameter <br> bb_notification_server_task_container_credentials_parameter | notification server container properties definition |
| Essential | bb_notification_server_task_container_essential <br> bb_notification_sidecar_server_task_container_essential | defines the server container as important in its cluster |
| Environment | bb_notification_server_task_container_java_vars <br> bb_notification_server_task_container_secretenv_definition <br> bb_notification_server_task_container_mon_secretenv <br> bb_notification_server_task_container_env <br> bb_notification_server_task_container_mon_env | environmental variable and property definitions for the server |
| Logging | bb_notification_server_task_container_log_driver <br> bb_notification_server_task_container_log_logsgroup <br> bb_notification_server_task_container_log_logsregion <br> bb_notification_server_task_container_log_logsprefix | variable definition for the collection of loggs|
| Loadbalancing | bb_notification_alb_arn <br> bb_notification_service_name | variables to attach the notification server to a loadbalancer and to configure health checks. |
| Autoscalling | bb_notification_service_autoscalling_policy_type <br> bb_notification_service_autoscalling_min_task <br> bb_notification_service_autoscalling_max_task <br> bb_notification_service_platform_version <br> bb_notification_service_count <br> bb_notification_service_mem_autoscalling_policy_name <br> bb_notification_service_cpu_autoscalling_policy_name <br> bb_notification_service_mem_autoscalling_tracking_scaling_target_value <br> bb_notification_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_notification_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_notification_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_notification_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_notification_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_notification_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_notification_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_notification_service_scheduled_autoscalling | autoscalling definitions for the notification server |
| Utility | bb_notification_service_awscli_enabled | AWS CLI active state for the server|
| Schedule | bb_notification_service_wake_cron <br> bb_notification_service_sleep_cron | variable definitions for the notification application's UAT server sleep & wake up time|

<br>

## **PosAPI server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Ports | bb_posapi_main_port <br> bb_posapi_tomcat_jmx_port | port definitions for the posapi server |
| Enabling service | bb_posapi_server_enabled | enables the PosAPI server task.|
| Regions | bb_active_region | PosAPI server's AWS region definition |
| DNS namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the PosAPI server dns |
| ECS task definition | bb_posapi_server_task_family_name <br> bb_posapi_server_task_networkmode <br> bb_posapi_server_task_executionRoleArn <br> bb_posapi_server_task_ecsmode <br> bb_posapi_server_task_cpu <br> bb_posapi_server_task_memory <br> bb_posapi_server_task_container_name <br> bb_posapi_server_task_container_image <br> bb_posapi_server_task_container_cpu <br> bb_posapi_server_task_container_memory <br> bb_posapi_server_task_container_credentials_parameter <br> bb_posapi_server_task_container_portmap_containerport <br> bb_posapi_server_task_container_portmap_hostport <br> bb_posapi_server_task_container_essential <br> bb_posapi_sidecar_server_task_container_essential | PosAPI container task variable definitions |
| Authorization | bb_posapi_server_payment_flow_auth_required | variable definition for payment flow authorization |
| Paths | bb_posapi_image_path | PosAPI image path definition |
| Properties | bb_posapi_server_task_container_java_vars | java properties for the PosAPI application|
| Environment | bb_posapi_server_task_container_secretenv_definition <br> bb_posapi_server_task_container_secretenv <br> bb_posapi_server_task_container_env <br> bb_posapi_server_task_container_mon_env <br> bb_posapi_server_task_container_mon_secretenv <br> bb_posapinginx_server_task_container_env | environmental variable definitions for the posapi server|
| Logging | bb_posapi_server_task_container_log_driver <br> bb_posapi_server_task_container_log_logsgroup <br> bb_posapi_server_task_container_log_logsregion <br> bb_posapi_server_task_container_log_logsprefix | variable definitions for collecting logs from the posapi server |
| Loadbalancing | bb_posapi_alb_arn <br> bb_posapi_service_name <br> bb_posapi_targetgroup_name <br> bb_posapi_targetgroup_protocol <br> bb_posapi_targetgroup_success_http_code <br> bb_posapi_targetgroup_hc_interval <br> bb_posapi_targetgroup_hc_timeout <br> bb_posapi_targetgroup_hc_healthycount <br> bb_posapi_targetgroup_hc_unhealthycount <br> bb_posapi_targetgroup_hc_path <br> bb_posapi_targetgroup_hc_protocol <br> bb_posapi_targetgroup_targettype | variable definitions to assign the PosAPI to a loadbalancer and configure health checks. |
| Autoscalling | bb_posapi_service_count <br> bb_posapi_service_platform_version <br> bb_posapi_service_hc_graceperiod <br> bb_posapi_service_autoscalling_policy_type <br> bb_posapi_service_autoscalling_min_task <br> bb_posapi_service_autoscalling_max_task <br> bb_posapi_service_mem_autoscalling_policy_name <br> bb_posapi_service_cpu_autoscalling_policy_name <br> bb_posapi_service_mem_autoscalling_tracking_scaling_target_value <br> bb_posapi_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_posapi_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_posapi_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_posapi_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_posapi_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_posapi_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_posapi_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_posapi_service_scheduled_autoscalling | autoscalling variable definitions for th PosAPI server|
| Utility | bb_posapi_service_awscli_enabled | AWS CLI active state definition|
| Schedule | bb_posapi_service_wake_cron <br> bb_posapi_service_sleep_cron | sleep and wake up time for the PosAPI's UAT server|

<br>

## **Scheduler server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Ports & URL | bb_scheduler_service_vars_main_base_url <br> bb_scheduler_main_port <br> bb_scheduler_int_port <br> bb_scheduler_tomcat_jmx_port | URL and port definitions for internal and external connections |
| Enabling service | bb_scheduler_server_enabled | enables the scheduler server.|
| Regions | bb_active_region | Scheduler server's AWS region definition |
| DNS namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the scheduler server |
| ECS task definition | bb_scheduler_server_task_family_name <br> bb_scheduler_server_task_networkmode <br> bb_scheduler_server_task_executionRoleArn <br> bb_scheduler_server_task_ecsmode <br> bb_scheduler_server_task_cpu <br> bb_scheduler_server_task_memory <br> bb_scheduler_server_task_container_name <br> bb_scheduler_server_task_container_image <br> bb_scheduler_server_task_container_cpu <br> bb_scheduler_server_task_container_memory <br> bb_scheduler_server_task_container_memoryReservation <br> bb_scheduler_server_task_container_credentials_parameter <br> bb_scheduler_server_task_container_essential <br> bb_scheduler_sidecar_server_task_container_essential | scheduler server ecs task definition |
| Properties | bb_scheduler_server_task_container_java_vars | java property definition for the scheduler application |
| Environment | bb_scheduler_server_task_container_secretenv_definition <br> bb_scheduler_server_task_container_mon_secretenv <br> bb_scheduler_server_task_container_env | Environmental variable definitions for the server |
| Logging | bb_scheduler_server_task_container_log_driver <br> bb_scheduler_server_task_container_log_logsgroup <br> bb_scheduler_server_task_container_log_logsregion <br> bb_scheduler_server_task_container_log_logsprefix | Variable definitions to collect container logs |
| Loadbalancing | bb_scheduler_alb_arn <br> bb_scheduler_service_name <br> bb_scheduler_targetgroup_name <br> bb_scheduler_targetgroup_protocol <br> bb_scheduler_ssl_targetgroup_name <br> bb_scheduler_ssl_targetgroup_protocol <br> bb_scheduler_targetgroup_success_http_code <br> bb_scheduler_targetgroup_hc_interval <br> bb_scheduler_targetgroup_hc_timeout <br> bb_scheduler_targetgroup_hc_healthycount <br> bb_scheduler_targetgroup_hc_unhealthycount <br> bb_scheduler_targetgroup_hc_path <br> bb_scheduler_targetgroup_hc_protocol <br> bb_scheduler_ssl_targetgroup_hc_protocol <br> bb_scheduler_targetgroup_targettype | variable definitions to assign the scheduler server to a loadbalancer and configure health checks.|
| Autoscalling | bb_scheduler_service_count <br> bb_scheduler_service_platform_version <br> bb_scheduler_service_hc_graceperiod <br> bb_scheduler_service_autoscalling_policy_type <br> bb_scheduler_service_autoscalling_min_task <br> bb_scheduler_service_autoscalling_max_task <br> bb_scheduler_service_mem_autoscalling_policy_name <br> bb_scheduler_service_cpu_autoscalling_policy_name <br> bb_scheduler_service_mem_autoscalling_tracking_scaling_target_value <br> bb_scheduler_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_scheduler_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_scheduler_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_scheduler_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_scheduler_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_scheduler_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_scheduler_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_scheduler_service_scheduled_autoscalling | autoscalling definitions for the scheduler server |
| Utility | bb_scheduler_service_awscli_enabled | AWS CLI active state for the server |
| Schedule | bb_scheduler_service_wake_cron <br> bb_scheduler_service_sleep_cron| sleep and wake up time for the scheduler application's UAT server |

<br>

## **Secure Core server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Ports | bb_securecore_main_port <br> bb_securecore_int_port <br> bb_securecore_tomcat_jmx_port | port definitions for internal and external connections |
| Enabling service | bb_securecore_server_enabled | enables the securecore server.|
| Regions | bb_active_region | Securecore server's AWS region definition |
| DNS namespace setup | bb_ctive_priv_dns_namespace | defines a private namespace for the securecore server |
| ECS task definition | bb_securecore_server_task_family_name <br> bb_securecore_server_task_networkmode <br> bb_securecore_server_task_executionRoleArn <br> bb_securecore_server_task_ecsmode <br> bb_securecore_server_task_cpu <br> bb_securecore_server_task_memory <br> bb_securecore_server_task_container_name <br> bb_securecore_server_task_container_image <br> bb_securecore_server_task_container_cpu <br> bb_securecore_server_task_container_memory <br> bb_securecore_server_task_container_memoryReservation <br> bb_securecore_server_task_container_credentials_parameter <br> bb_securecore_server_task_container_portmap_containerport <br> bb_securecore_server_task_container_portmap_hostport | Securecore server task definition |
| Essentials | bb_securecore_sidecar_server_task_container_essential <br> bb_securecore_server_task_container_essential | variable definitions to set the securecore server and its sidecar server as important in its cluster |
| Paths | bb_securecore_image_path <br> bb_securecore_download_path | path definitions for the securecore server's container image |
| Authentication | bb_securecore_server_owasp_resc <br> bb_securecore_server_auth_cache_ttl_mins <br> bb_securecore_server_max_login_attempt <br> bb_securecore_server_max_use_forward_headers | authentication variable definitions for connecting to the securecore server|
| Properties | bb_securecore_server_task_container_java_vars | java properties definition for the securecore server|
| Environments | bb_securecore_server_task_container_secretenv_definition <br> bb_securecore_server_task_container_secretenv <br> bb_securecorenginx_server_task_container_env <br> bb_securecore_server_task_container_mon_env_docker_env_tags <br> bb_securecore_server_task_container_mon_env <br> bb_securecore_server_task_container_log_env <br> bb_securecore_server_task_container_mon_secretenv | Environmental variable definitions for the securecore server |
| Logging | bb_securecore_server_task_container_log_driver <br> bb_securecore_server_task_container_log_logsgroup <br> bb_securecore_server_task_container_log_logsregion <br> bb_securecore_server_task_container_log_logsprefix | variable definitions to collect logs from the securecore server |
| Loadbalancing | bb_securecore_alb_arn <br> bb_securecore_service_name <br> bb_securecore_targetgroup_name <br> bb_securecore_http_targetgroup_name <br> bb_securecore_targetgroup_protocol <br> bb_securecore_targetgroup_port <br> bb_securecore_http_targetgroup_port <br> bb_securecore_ssl_targetgroup_name <br> bb_securecore_ssl_targetgroup_protocol <br> bb_securecore_targetgroup_success_http_code <br> bb_securecore_targetgroup_hc_interval <br> bb_securecore_targetgroup_hc_timeout <br> bb_securecore_targetgroup_hc_healthycount <br> bb_securecore_targetgroup_hc_unhealthycount <br> bb_securecore_targetgroup_hc_path <br> bb_securecore_targetgroup_hc_protocol <br> bb_securecore_targetgroup_hc_port <br> bb_securecore_ssl_targetgroup_hc_protocol <br> bb_securecore_targetgroup_targettype | variable definitions to assign the securecore server to an application load balancer as well as configure health checks|
| Autoscalling | bb_securecore_service_count <br> bb_securecore_service_platform_version <br> bb_securecore_service_hc_graceperiod <br> bb_securecore_service_autoscalling_policy_type <br> bb_securecore_service_autoscalling_min_task <br> bb_securecore_service_autoscalling_max_task <br> bb_securecore_service_mem_autoscalling_policy_name <br> bb_securecore_service_cpu_autoscalling_policy_name <br> bb_securecore_service_mem_autoscalling_tracking_scaling_target_value <br> bb_securecore_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_securecore_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_securecore_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_securecore_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_securecore_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_securecore_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_securecore_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_securecore_service_scheduled_autoscalling | Autoscalling variable definitions for the securecore server|
| Utility | bb_securecore_service_awscli_enabled | variable to define the active state of the AWS CLI |
 Schedule | bb_securecore_service_wake_cron <br> bb_securecore_service_sleep_cron | sleep and wake up time definition for the securecore's UAT servers |
| Proxy | bb_securecore_proxyserver_name <br> bb_securecore_proxyserver_port <br> bb_securecore_proxyserver_task_container_env <br> bb_securecore_network_lb_port | Proxy definitions for the server |

<br>

## **Template Engine server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_templateengine_server_enabled | enables the templateengine server.|
| Regions | bb_active_region | Templateengine server's AWS region definition |
| DNS namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the securecore server |
| ECS task definition | bb_templateengine_server_task_family_name <br> bb_templateengine_server_task_executionRoleArn <br> bb_templateengine_server_task_networkmode <br> bb_templateengine_server_task_ecsmode <br> bb_templateengine_server_task_cpu <br> bb_templateengine_server_task_memory <br> bb_templateengine_server_task_container_name <br> bb_templateengine_server_task_container_image <br> bb_templateengine_server_task_container_cpu <br> bb_templateengine_server_task_container_memory <br> bb_templateengine_server_task_container_memoryReservation <br> bb_templateengine_server_task_container_credentials_parameter <br> bb_templateengine_server_task_container_credentials_parameter <br> bb_templateengine_server_task_container_essential | Template Engine container task definition |
| Properties | bb_templateengine_server_task_container_java_vars | Java properties definition for the templateengine|
| Environment | bb_templateengine_server_task_container_secretenv_definition <br> bb_templateengine_server_task_container_env | Variables to define environmental variables for the template Engine server|
| Logging | bb_templateengine_server_task_container_log_driver <br> bb_templateengine_server_task_container_log_logsgroup <br> bb_templateengine_server_task_container_log_logsregion <br> bb_templateengine_server_task_container_log_logsprefix | variable definitions to collect server logs |
| Loadbalancing | bb_templateengine_alb_arn | variables to assign the template engine server to an application loadbalancer and to configure health checks|
| Service | bb_templateengine_service_name <br> bb_templateengine_service_count <br> bb_templateengine_service_platform_version | service property definition for the template engine |
| Autoscalling | bb_templateengine_service_autoscalling_policy_type <br> bb_templateengine_service_autoscalling_min_task <br> bb_templateengine_service_autoscalling_max_task <br> bb_templateengine_service_mem_autoscalling_policy_name <br> bb_templateengine_service_cpu_autoscalling_policy_name <br> bb_templateengine_service_mem_autoscalling_tracking_scaling_target_value <br> bb_templateengine_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_templateengine_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_templateengine_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_templateengine_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_templateengine_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_templateengine_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_templateengine_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_templateengine_service_scheduled_autoscalling | variable definitions to setup autoscalling for the template engine server.|
| Schedule | bb_templateengine_service_wake_cron <br> bb_templateengine_service_sleep_cron | sleep and wake up time for the template engine's UAT server|

<br>

## **USSD server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_ussd_server_enabled | enables the USSD server task.|
| Regions | bb_active_region | USSD server's AWS region definition |
| DNS namespace setup | bb_active_priv_dns_namespace | defines a private namespace for the USSD server |
| ECS task definition | bb_ussd_server_task_family_name <br> bb_ussd_server_task_executionRoleArn <br> bb_ussd_server_task_networkmode <br> bb_ussd_server_task_ecsmode <br> bb_ussd_server_task_cpu <br> bb_ussd_server_task_memory <br> bb_ussd_server_task_container_name <br> bb_ussd_server_task_container_image <br> bb_ussd_server_task_container_cpu <br> bb_ussd_server_task_container_memory <br> bb_ussd_server_task_container_memoryReservation <br> bb_ussd_server_task_container_credentials_parameter | USSD server's ECS task definition |
| Essential | bb_ussd_server_task_container_essential <br> bb_ussd_sidecar_server_task_container_essential | variables to set the USSD server as important in it's cluster |
| Properties | bb_ussd_server_task_container_java_vars | Java property definition for the USSD application |
| Environment | bb_ussd_server_task_container_env <br> bb_ussd_server_task_container_mon_env <br> bb_ussd_server_task_container_mon_secretenv <br> bb_ussd_server_task_container_secretenv_definition <br> bb_server_task_container_secretenv_definition <br> bb_ussd_nginx_server_task_container_env | variables to define the USSD application's environmental variables |
| Logging | bb_ussd_server_task_container_log_driver <br> bb_ussd_server_task_container_log_logsgroup <br> bb_ussd_server_task_container_log_logsregion <br> bb_ussd_server_task_container_log_logsprefix | variable definitions to collect logs |
| Loadbalancing | bb_ussd_alb_arn <br> bb_ussd_service_name <br> bb_ussd_targetgroup_name <br> bb_ussd_targetgroup_protocol <br> bb_ussd_targetgroup_success_http_code <br> bb_ussd_targetgroup_hc_interval <br> bb_ussd_targetgroup_hc_timeout <br> bb_ussd_targetgroup_hc_healthycount <br> bb_ussd_targetgroup_hc_unhealthycount <br> bb_ussd_targetgroup_hc_path <br> bb_ussd_targetgroup_hc_protocol <br> bb_ussd_targetgroup_targettype <br> bb_ussd_service_count <br> bb_ussd_service_platform_version <br> bb_ussd_service_hc_graceperiod | variables to assign the USSD application to an application loadbalancer and configure health checks|
| Autoscalling | bb_ussd_service_autoscalling_policy_type <br> bb_ussd_service_autoscalling_min_task <br> bb_ussd_service_autoscalling_max_task <br> bb_ussd_service_mem_autoscalling_policy_name <br> bb_ussd_service_cpu_autoscalling_policy_name <br> bb_ussd_service_mem_autoscalling_tracking_scaling_target_value <br> bb_ussd_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_ussd_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_ussd_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_ussd_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_ussd_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_ussd_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_ussd_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_ussd_service_scheduled_autoscalling | autoscalling variable definitions for the USSD server |
| Authentication | bb_ussd_service_vars_main_base_url <br> bb_ussd_service_vars_api_base_url <br> bb_ussd_service_vars_api_username <br> bb_ussd_service_vars_api_password <br> bb_ussd_service_vars_api_appref <br> bb_ussd_service_vars_slydepay_ussd_base_url | service authentication variable definition for the USSD application.|
| Providers | bb_ussd_service_vars_mtn_providers <br> bb_ussd_service_vars_atm_providers <br> bb_ussd_service_vars_vdc_providers | variable definitions for the services provided by USSD provider|
| Schedule | bb_ussd_service_wake_cron <br> bb_ussd_service_sleep_cron | sleep and wake up variable definitions for the USSD application's USSD server|

<br>

## **WebPos server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| ECS task definition | bb_webpos_server_credentials <br> bb_webpos_server_task_family_name <br> bb_webpos_server_task_executionRoleArn <br> bb_webpos_server_task_networkmode <br> bb_webpos_server_task_ecsmode <br> bb_webpos_server_task_cpu <br> bb_webpos_server_task_memory <br> bb_webpos_server_task_container_name <br> bb_webpos_server_task_container_image <br> bb_webpos_server_task_container_cpu <br> bb_webpos_server_task_container_memory <br> bb_webpos_sidecar_server_task_container_essential <br> bb_webpos_server_task_container_credentials_parameter <br> bb_webpos_server_task_container_essential | WebPos ECS container task definition |
| Environment | bb_webpos_server_task_container_env <br> bb_webposnginx_server_task_container_env <br> bb_webpos_server_task_container_mon_env <br> bb_webpos_server_task_container_secretenv_definition <br> bb_webpos_server_task_container_secretenv <br> bb_webpos_server_task_container_mon_secretenv | environmental variable definitions for the WebPos server |
| Logging | bb_webpos_server_task_container_log_driver <br> bb_webpos_server_task_container_log_logsgroup <br> bb_webpos_server_task_container_log_logsregion <br> bb_webpos_server_task_container_log_logsprefix | Variable definitions to collect logs |
| Loadbalancing | bb_webpos_alb_arn <br> bb_webpos_service_name <br> bb_webpos_targetgroup_name <br> bb_webpos_targetgroup_protocol <br> bb_webpos_targetgroup_success_http_code <br> bb_webpos_targetgroup_hc_interval <br> bb_webpos_targetgroup_hc_timeout <br> bb_webpos_targetgroup_hc_healthycount <br> bb_webpos_targetgroup_hc_unhealthycount <br> bb_webpos_targetgroup_hc_path <br> bb_webpos_targetgroup_hc_protocol <br> bb_webpos_targetgroup_targettype | variable definitions to assign the webpos server to an application load bakancer as well as configure health checks.|
| Autoscalling | bb_webpos_service_platform_version <br> bb_webpos_service_hc_graceperiod <br> bb_webpos_service_autoscalling_policy_type <br> bb_webpos_service_autoscalling_min_task <br> bb_webpos_service_autoscalling_max_task  <br> bb_webpos_service_mem_autoscalling_policy_name <br> bb_webpos_service_cpu_autoscalling_policy_name <br> bb_webpos_service_mem_autoscalling_tracking_scaling_target_value <br> bb_webpos_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_webpos_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_webpos_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_webpos_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_webpos_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_webpos_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_webpos_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_webpos_service_scheduled_autoscalling | Autoscalling variable definitions for the WEBPOS server |
Schedule | bb_webpos_service_wake_cron <br> bb_webpos_service_sleep_cron | variable definitions to set a sleep and wake up time for the WEBPOS's UAT server|
| Utility | bb_webpos_service_awscli_enabled | variable definitions to for the active state of the AWS CLI on the server |

<br>

## **Mongo Databases server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Package Installation | util_filesystem_install_packages_direct_list <br> util_filesystem_install_pip_package_list | variables definitions to install database dependencies |
| Enabling packages | util_filesystem_enable <br> aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable <br> aws_s3_enable | variable definitions to enable or disable specific packages |
| Paths | aws_s3_pull_object_details | Mongo seed file location definition |
| Unarchiving | mongofamily_server_seed_unarchive_details | Variable definitions to unarchive Mongo server seed file |
| Properties | mongofamily_server_seed_dump_folder_details | variables to deine Mongo seed dump properties |

<br>

## **MySQL Database server variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Database Creation | jumpbox_mysql_create_database_details | Variable definitions for creating MySQL database specifying root credentials and port|

<br>

## **GhafricXpressGlo Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghafricxpressglo_vhost_file  | variable definitions to set up GhafricXpressGlo virtual host|
| Proxy Upstream| ghafricxpressglo_upstream_host1 <br> ghafricxpressglo_upstream_host1_mon_type <br> ghafricxpressglo_upstream_host1_mon_scheme| variables to setup host proxy upstream|
| Enabling versions and packages | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable nginx webserver version and server roles |
| Webserver Configuration and Properties | webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | Nginx webserver config details definition |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver|
| ELK| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to configure ELK|

<br>

## **GhAirTigoBankInt Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghairtigobankint_vhost_file <br> ghairtigobankint_upstream_host1 <br> ghairtigobankint_upstream_host1_mon_type <br> ghairtigobankint_upstream_host1_mon_scheme | variable definitons to setup VHOST on the server |
| Enabling versions and packages | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable nginx webserver versions and server roles |
| Webserver Configuration and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure Nginx |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver|
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to configure ELK|

<br>

## **Ghgwcl Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghgwcl_vhost_file <br> ghgwcl_upstream_host1 <br> ghgwcl_upstream_host1_mon_type <br> ghgwcl_upstream_host1_mon_scheme | variable definitions to setup a virtual host on the proxy server|
| Enabling webserver version | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable nginx webserver version and functions |
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure nginx |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver |
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to configure ELK|

<br>

## **GhMTNOva Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghmtnova_vhost_file <br> ghmtnova_upstream_host1 <br> ghmtnova_upstream_host1_mon_type <br> ghmtnova_upstream_host1_mon_scheme <br> ghmtnova_upstream_host2 <br> ghmtnova_upstream_host2_mon_type <br> ghmtnova_upstream_host2_mon_scheme | variable definitions to setup virtual hosts on the proxy server |
| Enabling webserver version | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable nginx version and functions |
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure nginx |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver |
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to setup ELK |

<br>

## **Ghria Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghria_vhost_file <br> ghria_upstream_host1 <br> ghria_upstream_host1_mon_type <br> ghria_upstream_host1_mon_scheme | variable definitions to setup a virtual host for RIA on the proxy server|
| Enabling version | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable specific nginx versions |
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure the nginx webserver |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | vvariable definitions to enable validation and restart functions of the webserver |
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to setup ELK |

<br>

## **Ghstanlib Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghstanlib_vhost_file <br> ghstanlib_upstream_host1 <br> ghstanlib_upstream_host1_mon_type <br> ghstanlib_upstream_host1_mon_scheme | variable definitions to setup a virtual host on the proxy server.|
| Enabling webserver versions | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definittions to enable specific Nginx webserver versions|
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure nginx and set it's properties|
| Enabling webserver properties & functions | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver|
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name |variable definitions to setup ELK for the proxy service |

<br>

## **Ghsurfline Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghsurfline_vhost_file <br> ghsurfline_upstream_host1 <br> ghsurfline_upstream_host1_mon_type <br> ghsurfline_upstream_host2 <br> ghsurfline_upstream_host2_mon_type <br> ghsurfline_upstream_host2_mon_scheme | variable definitions to setup a virtual host on the proxy server |
| Enabling versions | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variables to enable specific Nginx versions |
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to setup nginx webserver and it's properties|
| Enabling webserver properties & functions | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver |
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variables to setup ELK to collect and ship data|

<br>

## **Ghtotal Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_ghtotal_vhost_file <br> ghtotal_upstream_host1 <br> ghtotal_upstream_host1_mon_type <br> ghtotal_upstream_host1_mon_scheme | variables to setup a virtual host on the proxy server for the service |
| SSL Secrets and directory path | total_client_ssl_folder_path <br> util_filesystem_create_directory_with_pem_details_dict  | path definitions to create and store the client's ssl secrets |
| Enabling versions and packages | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable <br> aws_s3_enable | variable definitions to enable specific nginx webserver versions and essential packages |
| SSL credentials | total_client_ssl_cert <br> total_client_ssl_key | variable definitions for Total's ssl credentials|
| S3 object paths | aws_s3_pull_object_details | variable definitions for the directory where the ssl credentials are stored in Amazon S3|
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to setup nginx proxy configurations |
| Enabling webserver properties & functions | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver |
| ELK setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to setup ELK|

<br>

## **Guinea_marketplace variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| ECS task definition | bb_marketplace_server_task_family_name <br> bb_marketplace_server_task_executionRoleArn <br> bb_marketplace_server_task_networkmode <br> bb_marketplace_server_task_ecsmode <br> bb_marketplace_server_task_cpu <br> bb_marketplace_server_task_memory <br> bb_marketplace_server_task_container_name <br> bb_marketplace_server_task_container_image <br> bb_marketplace_server_task_container_cpu <br> bb_marketplace_server_task_container_memory <br> bb_marketplace_server_task_container_credentials_parameter <br> bb_marketplace_server_task_container_essential <br> bb_marketplace_sidecar_server_task_container_essential | Marketplace ECS task and sidecar definition |
| Environment | bb_marketplace_server_task_container_env <br> bb_marketplacenginx_server_task_container_env <br> bb_marketplace_server_task_container_mon_env <br> bb_marketplace_server_task_container_secretenv_definition <br> bb_marketplace_server_task_container_secretenv | environmental variable definitions for the marketplace server |
| Logging | bb_marketplace_server_task_container_log_driver <br> bb_marketplace_server_task_container_log_logsgroup <br> bb_marketplace_server_task_container_log_logsregion <br> bb_marketplace_server_task_container_log_logsprefix | variable definitons to collect logs from the container |
| Loadbalancing | bb_marketplace_alb_arn <br> bb_marketplace_service_name <br> bb_marketplace_targetgroup_name <br> bb_marketplace_targetgroup_protocol <br> bb_marketplace_targetgroup_success_http_code <br> bb_marketplace_targetgroup_hc_interval <br> bb_marketplace_targetgroup_hc_timeout <br> bb_marketplace_targetgroup_hc_healthycount <br> bb_marketplace_targetgroup_hc_unhealthycount <br> bb_marketplace_targetgroup_hc_path <br> bb_marketplace_targetgroup_hc_protocol <br> bb_marketplace_targetgroup_targettype <br> bb_marketplace_service_count <br> bb_marketplace_service_platform_version <br> bb_marketplace_service_hc_graceperiod | variable definitions to assign the server to an application load balancer and configure health checks|
| Autoscalling | bb_marketplace_service_autoscalling_policy_type <br> bb_marketplace_service_autoscalling_min_task <br> bb_marketplace_service_autoscalling_max_task <br> bb_marketplace_service_mem_autoscalling_policy_name <br> bb_marketplace_service_cpu_autoscalling_policy_name <br> bb_marketplace_service_mem_autoscalling_tracking_scaling_target_value <br> bb_marketplace_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_marketplace_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_marketplace_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_marketplace_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_marketplace_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_marketplace_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_marketplace_service_cpu_autoscalling_tracking_scalin_cooldown <br> bb_marketplace_service_scheduled_autoscalling | autoscalling variable definitions for the guinea marketplace ecs task|
| Utilities | bb_marketplace_service_awscli_enabled | AWS CLI active state definition |
| Schedule | bb_marketplace_service_wake_cron <br> bb_marketplace_service_sleep_cron | sleep and wake up variable definitions for the market places' UAT environment|

<br>

## **Mongo_arbiter variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Filesystem and packages setup| util_filesystem_install_packages_direct_list <br> util_filesystem_enable <br> aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable | variable definitions to enable the filesystem and install packages |
| Mongo server details| mongofamily_server_common_config_create_directory_with_pem_details <br> mongofamily_server_common_config_details | common config variable definitions for percona server|
| Amazon S3 setup | aws_s3_enable <br> aws_s3_pull_object_details | variable definitions to enable and pull S3 object details|
| Percona database setup | mongofamily_percona_mongo_enable <br> mongofamly_percona_release_version <br> mongofamly_percona_release_enable_key <br> mongofamly_percona_release_update <br> mongofamily_server_release_name <br> mongofamily_percona_install_components_list <br> mongofamily_server_common_random_command_details <br> mongofamily_server_common_random_command_details_final | mongo percona server setup variable definitions|
| Database security | mongofamily_server_security_enabled <br> mongofamily_security_util_enabled <br> mongofamily_security_util_filesystem_create_directory_with_pem_details <br> mongofamily_security_util_filesystem_copy_files_details <br> mongofamily_security_replace_conf_details <br> mongofamily_security_server_state_details <br> mongofamily_security_wait_for <br> mongofamily_security_deploy_wait_details | variable definitions to setup and configure database security|
| Mongo replicaset setup | mongofamily_server_replicatset_enabled <br> mongofamily_server_replica_replace_conf_details <br> mongofamily_server_replica_server_state_details <br> mongofamily_server_replica_wait_for <br> mongofamily_server_replica_deploy_wait_details | variable definitions to setup and configure the database's replica set |
| Database security | mongofamily_server_security_enabled <br> mongofamily_security_util_enabled <br> mongofamily_security_util_filesystem_create_directory_with_pem_details <br> mongofamily_security_util_filesystem_copy_files_details <br> mongofamily_security_users_details <br> mongofamily_security_replace_conf_details <br> mongofamily_security_server_state_details <br> mongofamily_security_wait_for <br> mongofamily_security_deploy_wait_details | variable definitions to setup and configure the database's security |
| Mongo replicaset setup | mongofamily_server_createreplica_enabled <br> mongofamily_server_replica_replace_conf_details <br> mongofamily_server_replica_server_state_details <br> mongofamily_server_replica_wait_for <br> mongofamily_server_replica_deploy_wait_details <br> mongofamily_server_replica_designated_master <br> mongofamily_server_replica_arbiter_members <br> mongofamily_server_common_config_details| variable definitions to setup and configure the database replica set|
| Database User | global_var_ubuntu_user | Mongo user definition|

<br>

## **Mongo database variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Filesystem, directories and packages setup | util_filesystem_enable <br> util_filesystem_install_packages_direct_list <br> aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable <br> util_filesystem_create_directory_with_pem_details | variable definitions to setup the database filesystem and install packages |
| Mongo Target | master_mongo_target_helper | variable definitions for the master mongo sync target|
| S3 object setup | aws_s3_enable <br> aws_s3_pull_object_details | variable definitions to setup and pull S3 object details |
| Percona database setup | mongofamily_percona_mongo_enable <br> mongofamly_percona_release_version <br> mongofamly_percona_release_enable_key <br> mongofamly_percona_release_update <br> mongofamily_server_release_name <br> mongofamily_percona_install_components_list <br> mongofamily_server_common_random_command_details <br> mongofamily_server_common_random_command_details_final | mongo percona server setup |

<br>

## **Monitoring_InsightOps variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Agent setup | monitoringfamily_install_file <br> monitoringfamily_r7insightops_config_path <br> monitoringfamily_enable_r7insightops <br> monitoringfamily_r7insightops_agent_directory <br> monitoringfamily_r7insightops_agent_online_download_url <br> monitoringfamily_r7insightops_agent_download_details <br> monitoringfamily_r7insightops_agent_manual_install_details <br> monitoringfamily_r7insightops_dependent_packages <br> monitoringfamily_r7insightops_create_directory_with_pem_details| Variable definitions to setup and configure the server for the insightOps monitoring agent|
| Agent Logging and templating | monitoringfamily_nginx_ansiblevhost_accesslog <br> monitoringfamily_nginx_ansiblevhost_errorlog <br> monitoringfamily_r7insightops_agent_templating_details| variable definitions to configure templating and collect logs|

<br>

## **MySQL database variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Filesystem, directories and packages setup | util_filesystem_enable <br> util_filesystem_install_package_list <br> perconamysql_configure_repo_details| variable definitions to setup the database filesystem and install essential packages |
| Percona xtradb setup | perconamysql_xtradb_cluster_name <br> perconamysql_xtradb_cluster_enable <br> perconamysql_xtradb_cluster_name_version <br> perconamysql_xtradb_cluster_stop_for_repl <br> perconamysql_xtradb_cluster_port <br> perconamysql_xtradb_cluster_config_rootpath <br> perconamysql_xtradb_cluster_client_conf_path <br> perconamysql_xtradb_cluster_port_details <br> perconamysql_xtradb_cluster_password <br> perconamysql_xtradb_cluster_replacepassword_enable <br> perconamysql_xtradb_cluster_sst_username <br> perconamysql_xtradb_cluster_sst_password <br> perconamysql_xtradb_cluster_setup_users_details <br> perconamysql_xtradb_cluster_templating_details <br> perconamysql_xtradb_cluster_first_node <br> perconamysql_xtradb_cluster_all_node_restart_enable <br> perconamysql_xtradb_cluster_bootstrap_path | variable definitions to setup and configure Percona Xtradb to replicate data on cluster nodes|

<br>

## **Proxy_Default variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_default_vhost_file | variable definitions to setup the default virtual host configuration|
| Logging | proxy_default_log_access_file <br> proxy_default_log_error_file | variable definitions to configure where collected logs are kept|
| Proxy server filesystem | util_filesystem_enable <br> util_filesystem_create_directory_with_pem_details_dict|
| Enabling Packages| aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable <br> aws_s3_enable <br> aws_s3_pull_object_details| variable feinitions to enable essential webserver packages|
| Enabling webserver and role properties | webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable | variable definitions to enable nginx webserver version and functions |
| Webserver configurations and properties | webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variable definitions to configure nginx |
| Enabling webserver properties | webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable validation and restart functions of the webserver |
| Elasticbeats setup | elasticbeats_hearbeat_log_dir <br> elasticbeats_hearbeat_log_filename <br> elastibeats_heartbeat_version <br> elasticbeats_remove_configuration_details <br> elasticbeats_installation_details <br> elasticbeats_configuration_details <br> elasticbeats_systemd_details| variable definitions to configure Elasticbeats|
| Proxy server monitoring | monitoringfamily_install_file <br> monitoringfamily_r7insightops_config_path <br> monitoringfamily_enable_r7insightops <br> monitoringfamily_r7insightops_agent_directory <br> monitoringfamily_r7insightops_agent_download_details <br> monitoringfamily_r7insightops_agent_manual_install_details <br> monitoringfamily_r7insightops_dependent_packages <br> monitoringfamily_r7insightops_create_directory_with_pem_details <br> monitoringfamily_r7insightops_accesslog_name <br> monitoringfamily_r7insightops_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data | variable definitions to setup rapid7insightops to monitor the proxy server|

<br>

## **Proxy_Forward_Gh_AfrxprssAirteltigo variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_afrxprssairteltigo_vhost_file| variable definitions to setup virtual host configuration|
| Logging |proxy_forward_gh_afrxprssairteltigo_log_access_file <br> proxy_forward_gh_afrxprssairteltigo_log_error_file| variable definitions to configure where collected logs are kept|
| Proxy Upstream | proxy_forward_gh_afrxprssairteltigo_upstream_host1 <br> proxy_forward_gh_afrxprssairteltigo_upstream_host1_mon_type <br> proxy_forward_gh_afrxprssairteltigo_upstream_host1_mon_scheme | variable definitions to configure proxy data upstream parameters|
| Enabling and configuring roles and packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable proxy server roles and configure them|
| Elasticbeats Setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variable definitions to configure elasticbeats|
| Monitoring | monitoringfamily_r7insightops_forward_gh_afrxprssairteltigo_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_afrxprssairteltigo_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightops agent to monitor the proxy connection |

<br>

## **Proxy_Forward_Gh_AfrxprssGlo variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_afrxprssglo_vhost_file | variable definitions to setup virtual host configuration|
| Logging | proxy_forward_gh_afrxprssglo_log_access_file <br> proxy_forward_gh_afrxprssglo_log_error_file| Variable deinitions to configure where collected log are stored.|
| Proxy Upstream | proxy_forward_gh_afrxprssglo_upstream_host1 <br> proxy_forward_gh_afrxprssglo_upstream_host1_mon_type <br> proxy_forward_gh_afrxprssglo_upstream_host1_mon_scheme| variable definitions to configure proxy data upstream parameters|
| Enabling roles and installing packagages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details | variable definitions to enable webserver family roles and install packages|
|Webserver Configuration | webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to configure nginx webserver and to enable specific functions|
| Elasticbeats setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats on the proxy host|
| Monitoring | monitoringfamily_r7insightops_forward_gh_afrxprssglo_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_afrxprssglo_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightops agent to monitor the proxy host|

<br>

## **Proxy_Forward_Gh_AfrxprssGlo variables**
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

## **Proxy_Forward_Gh_AirtelTigoBankIntegration variables**
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

## **Proxy_Forward_Gh_AppsnmobAirtelTigo variables**
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

## **Proxy_Forward_Gh_Ghipss variables**
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

## **Proxy_Forward_Gh_Gwcl variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_gwcl_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_gh_gwcl_log_access_file <br> proxy_forward_gh_gwcl_log_error_file| virtual host's log file variable definition|
| Proxy Upstream| proxy_forward_gh_gwcl_upstream_host1 <br> proxy_forward_gh_gwcl_upstream_host1_mon_type <br> proxy_forward_gh_gwcl_upstream_host1_mon_scheme| proxy data upstream variable definition|
| Enabling Webserver roles and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to enable webserver roles and install packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variable definitions to configure the proxy webserver|
| Elasticbeats setup | elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats|
| Monitoring | monitoringfamily_r7insightops_forward_gh_gwcl_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_gwcl_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps to collect logs from the proxy host|

<br>

## **Proxy_Forward_Gh_MtnAirtime variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_mtnairtime_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_gh_mtnairtime_log_access_file <br> proxy_forward_gh_mtnairtime_log_error_file <br> proxy_forward_gh_mtnairtime_access_log <br> proxy_forward_gh_mtnairtime_error_log | virtual host's log file variable definition|
| Proxy Upstream | proxy_forward_gh_mtnairtime_upstream_host1 <br> proxy_forward_gh_mtnairtime_upstream_host1_mon_type <br> proxy_forward_gh_mtnairtime_upstream_host1_mon_scheme| proxy data upstream variable definition|
| Enabling webserver roles and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details| variable definitions to enable the webserver_family role and to install the webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to configure the proxy webserver|
| Elasticbeats| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to configure elasticbeats for data shipping|
| Monitoring | monitoringfamily_r7insightops_forward_gh_mtnairtime_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_mtnairtime_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data|

<br>

## **Proxy_Forward_Gh_MtnDataBundle variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_mtndatabundle_vhost_file| | virtual host configuration file definition|
| Logging | proxy_forward_gh_mtndatabundle_log_access_file <br> proxy_forward_gh_mtndatabundle_log_error_file| virtual host's log file variable definition|
| Proxy Upstream | proxy_forward_gh_mtndatabundle_upstream_host1 <br> proxy_forward_gh_mtndatabundle_upstream_host1_mon_type <br> proxy_forward_gh_mtndatabundle_upstream_host1_mon_scheme| proxy data upstream variable definition|
| Enabling webserver roles and installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled| variable definitions to enable webserver role and install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variable definitions to configure the proxy webserver|
| Elasticbeats Setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to setup and configure elasticbeats to ship data|
| Monitoring | monitoringfamily_r7insightops_forward_gh_mtndatabundle_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_mtndatabundle_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps agent to monitor the proxy host and connection|


## **Proxy_Forward_Gh_MtnFttxBundle variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_mtnfttxbundle_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_gh_mtnfttxbundle_log_access_file <br> proxy_forward_gh_mtnfttxbundle_log_error_file| virtual host's log file variable definition|
| Proxy Upstream| proxy_forward_gh_mtnfttxbundle_upstream_host1 <br> proxy_forward_gh_mtnfttxbundle_upstream_host1_mon_type <br> proxy_forward_gh_mtnfttxbundle_upstream_host1_mon_scheme| proxy data upstream variable definition|
| Enabling webserver roles and Installing packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_install_details| variable definitions to enable webserver roles and to install webserver packages|
| Webserver Configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variable definitions to configure the proxy webserver|
| Elasticbeats Setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions to setup and configure elasticbeats to ship data|
| Monitoring | monitoringfamily_r7insightops_forward_gh_mtnfttxbundle_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_mtnfttxbundle_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rrapid7insightOps agent to monitor the proxy host and connection|

<br>

## **Proxy_Forward_Gh_StanbicDataPower variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_stanbicdatapower_vhost_file | virtual host configuration file definition|
| Proxy Upstream | forward_gh_stanbicdatapower_upstream_host1 <br> forward_gh_stanbicdatapower_upstream_host2 <br> forward_gh_stanbicdatapower_upstream_host1_mon_type <br> forward_gh_stanbicdatapower_upstream_host1_mon_scheme| proxy data upstream variable definition|
| SSL | forward_gh_stanbicdatapower_ssl_cert <br> forward_gh_stanbicdatapower_ssl_key <br> forward_gh_stanbicdatapower_client_ssl_folder_path| SSL setup variable definitions|
| Logging| proxy_forward_gh_stanbicdatapower_log_access_file <br> proxy_forward_gh_stanbicdatapower_log_error_file| log files definition|
| FIlesystem Setup| util_filesystem_enable <br> util_filesystem_create_directory_with_pem_details_dict| variable definitions to enable and setup a filesystem on the virtual host|
| Enabling webserver roles and installing packages| aws_install_python_pip_enable <br> aws_pip_install_boto_enable <br> aws_install_awscli_enable <br> aws_s3_pull_object_details <br> webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details | variables to enable webserver roles and install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash|  variable definitions to configure the proxy web server|
| Elasticbeats Setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variable definitions for elasticbeats to ship logs.|
| Monitoring| billbox_r7insightops_config_path <br> forward_gh_stanbicdatapower_r7insightops_access_destination <br> forward_gh_stanbicdatapower_r7insightops_error_destination <br> monitoringfamily_r7insightops_forward_gh_stanbicdatapower_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_stanbicdatapower_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variable definitions to configure rapid7insightOps to monitor the proxy server and connection|

<br>

## **Proxy_Forward_Gh_VodafoneCash variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_vodafonecash_vhost_file |virtual host configuration file definition|
| Proxy Upstream Host| proxy_forward_gh_vodafonecash_upstream_host1 <br> proxy_forward_gh_vodafonecash_upstream_host1_mon_type <br> proxy_forward_gh_vodafonecash_upstream_host1_mon_scheme| proxy host data upstream variable definition|
| Logging| proxy_forward_gh_vodafonecash_log_access_file <br> proxy_forward_gh_vodafonecash_log_error_file| proxy log files definition|
| Enabling webserver roles and installing webserver packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable webserverfamily role and to install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_hash_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variables to configure the proxy webserver|
| Elasticbeats| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variables to configure elasticbeats to ship data|
| Monitoring| monitoringfamily_r7insightops_forward_gh_vodafonecash_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_vodafonecash_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variables to configure repid7insightOps to monitor the proxy server and connection|

<br>

## **Proxy_Forward_Gh_ZeePayMomo variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_gh_zeepaymomo_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_gh_zeepaymomo_log_access_file <br> proxy_forward_gh_zeepaymomo_log_error_file | proxy log files definition|
|Proxy Upstream| proxy_forward_gh_zeepaymomo_upstream_host1 <br> proxy_forward_gh_zeepaymomo_upstream_host1_mon_type <br> proxy_forward_gh_zeepaymomo_upstream_host1_mon_scheme| proxy host data upstream variable definition|
| Enabling Webserver role and installing webserver packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled | variable definitions to enable webserver roles and to install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variables to configure the proxy websever|
| Elasticbeats| elasticbeats_configuration_details <br> elasticbeats_systemd_details| variables to setup elasticbeats to ship logs|
| Monitoring| monitoringfamily_r7insightops_forward_gh_zeepaymomo_accesslog_name <br> monitoringfamily_r7insightops_forward_gh_zeepaymomo_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variables to setup and configure rapid7insightOps agent to monitor the proxy host and connection|
| Proxy TargetGroup| proxy_forward_gh_zeepaymomoTG| variables to set the target group for the proxy server LB|


## **Proxy_Forward_ZW_Ecocash variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_zw_ecocash_vhost_file | virtual host configuration file definition|
| Logging| proxy_forward_zw_ecocash_log_access_file <br> proxy_forward_zw_ecocash_log_error_file| proxy log files definition|
| Proxy Upstream | proxy_forward_zw_ecocash_upstream_host1 <br> proxy_forward_zw_ecocash_upstream_host1_mon_host1 <br> proxy_forward_zw_ecocash_upstream_host1_mon_type <br> proxy_forward_zw_ecocash_upstream_host1_mon_scheme| proxy host data upstream variable definition|
| Enabling webserver roles and installing webserver packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_install_details| variables to enable webserver roles and to install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variables to configure the installed proxy web server|
| Elasticbeats| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variables to setup elasticbeats for shipping data|
monitoringfamily_r7insightops_agent_templating_details:
| Monitoring| monitoringfamily_r7insightops_forward_zw_ecocash_accesslog_name <br> monitoringfamily_r7insightops_forward_zw_ecocash_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_data| variables to configure rapid7insightOps to monitor the proxy host and connection|


<br>

## **Proxy_Forward_ZW_Econet variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_forward_zw_econet_vhost_file | virtual host configuration file definition|
|Logging| proxy_forward_zw_econet_log_access_file <br> proxy_forward_zw_econet_log_error_file | proxy log files definition|
| Proxy Upstream| forward_zw_econet_upstream_postpaid_host1 <br> forward_zw_econet_upstream_data_host1 <br> forward_zw_econet_upstream_postpaid_host1_mon_type <br> forward_zw_econet_upstream_postpaid_host1_mon_scheme | variables to define the proxy upstream config for the host|
| Webserver roles and packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_install_details| variables to enable webserver roles and install webserver packages|
| webserver configuration | webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variables to configure the proxy webserver|
| Elasticbeats| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name | variables to setup and configure elasticbeats for shipping data|
| Monitoring| monitoringfamily_r7insightops_forward_zw_econet_accesslog_name <br> monitoringfamily_r7insightops_forward_zw_econet_errorlog_name <br> monitoringfamily_r7insightops_agent_templating_details <br> monitoringfamily_r7insightops_agent_templating_data| variables to configure rapid7insightOps to monitor the proxy host and connection|

<br>

## **Proxy_Reverse_ZW_Econet variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup | proxy_zweconet_vhost_file | virtual host configuration file definition|
| Proxy Upstream Host| zweconet_upstream_host1 <br> zweconet_upstream_host1_mon_type <br> zweconet_upstream_host1_mon_scheme| variables to define the proxy upstream config for the host|
| Webserver roles and packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_install_details| variables to enable webserver roles and install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash| variables to configure webserver reverse proxy|

<br>

## **Script_Mysql variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Scripts| jumpbox_mysql_execute_script_dependencies_apps_list| variable definition for mysql scripts that install and execute mysql packages|
| Script Vars| jumpbox_mysql_execute_script_details| variable to set mysql config data. These data include app credentials and database config data|


## **SecureCardHandler variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling service | bb_securecardhandler_server_enabled| variable to enable the securecardhandler service|
| Region setup | smartgrid_active_region| variable to set the active region of the service|
| Service Namespace| smartgrid_active_priv_dns_namespace| variable to setup a private dns namespace for the service|
| Service Task Definition| bb_securecardhandler_server_task_family_name <br> bb_securecardhandler_server_task_executionRoleArn <br> bb_securecardhandler_server_task_networkmode <br> bb_securecardhandler_server_task_ecsmode <br> bb_securecardhandler_server_task_cpu <br> bb_securecardhandler_server_task_memory <br> bb_securecardhandler_server_task_container_name <br> bb_securecardhandler_server_task_container_image <br> bb_securecardhandler_server_task_container_cpu <br> bb_securecardhandler_server_task_container_memory <br> bb_securecardhandler_server_task_container_memoryReservation <br> bb_securecardhandler_server_task_container_credentials_parameter <br> bb_securecardhandler_server_task_container_essential <br> bb_securecardhandler_sidecar_server_task_container_essential <br> bb_securecardhandler_server_task_container_java_vars| ECS task definition variables for the securecardhandler|
| Environment| bb_securecardhandler_server_task_container_mon_env <br> bb_securecardhandler_server_task_container_env <br> bb_securecardhandler_server_task_container_secret_rawenv <br> bb_securecardhandler_server_task_container_mon_secretenv <br> bb_securecardhandler_server_task_container_secretenv <br> bb_securecardhandler_nginx_server_task_container_env | environmental variable definitions for the Securecardhanndler server|
| Logging | bb_securecardhandler_server_task_container_log_driver <br> bb_securecardhandler_server_task_container_log_logsgroup <br> bb_securecardhandler_server_task_container_log_logsregion <br> bb_securecardhandler_server_task_container_log_logsprefix| variables to configure and collect service task logs|
| Loadbalancing| bb_securecardhandler_alb_arn <br> bb_securecardhandler_service_name <br> bb_securecardhandler_targetgroup_name <br> bb_securecardhandler_targetgroup_protocol <br> bb_securecardhandler_targetgroup_success_http_code <br> bb_securecardhandler_targetgroup_hc_interval <br> bb_securecardhandler_targetgroup_hc_timeout <br> bb_securecardhandler_targetgroup_hc_healthycount <br> bb_securecardhandler_targetgroup_hc_unhealthycount <br> bb_securecardhandler_targetgroup_hc_path <br> bb_securecardhandler_targetgroup_hc_protocol <br> bb_securecardhandler_targetgroup_hc_port <br> bb_securecardhandler_targetgroup_targettype| variables to attach the service task to a loadbalancer and to configure health checks.|
| Autoscalling| bb_securecardhandler_service_count <br> bb_securecardhandler_service_platform_version <br> bb_securecardhandler_service_hc_graceperiod <br> bb_securecardhandler_service_autoscalling_policy_type <br> bb_securecardhandler_service_autoscalling_min_task <br> bb_securecardhandler_service_autoscalling_max_task <br> bb_securecardhandler_service_mem_autoscalling_policy_name <br> bb_securecardhandler_service_cpu_autoscalling_policy_name <br> bb_securecardhandler_service_mem_autoscalling_tracking_scaling_target_value <br> bb_securecardhandler_service_cpu_autoscalling_tracking_scaling_target_value <br> bb_securecardhandler_service_mem_autoscalling_tracking_scaling_metric_spec <br> bb_securecardhandler_service_cpu_autoscalling_tracking_scaling_metric_spec <br> bb_securecardhandler_service_mem_autoscalling_tracking_scalout_cooldown <br> bb_securecardhandler_service_mem_autoscalling_tracking_scalin_cooldown <br> bb_securecardhandler_service_cpu_autoscalling_tracking_scalout_cooldown <br> bb_securecardhandler_service_cpu_autoscalling_tracking_scalin_cooldown| variables to set autoscalling properties of the securecardhandler task|
| Utility| bb_securecardhandler_service_awscli_enabled | variables to enable the AWS CLI and its components|
| Service Proxy| bb_securecardhandler_proxyserver_listen_port | variable to configure securecardhandler's proxy server listening port|
| Transaction Processing | bb_securecardhandler_procesor <br> bb_securecardhandler_transaction_url_success <br> bb_securecardhandler_transaction_url_error| Transaction processor and url definition |
| Redis| bb_securecardhandler_redis_host <br> bb_securecardhandler_redis_port | variables to set redis database host and port|
| Public IP| bb_securecardhandler_service_assign_public_ip| variable to set securecardhandler's public Ip status|
| Essentials| bb_securecardhandler_server_task_container_datadog_essential <br> bb_securecardhandler_server_task_container_envoy_essential| variables to set datadog and envoy agents as essential to the startup of the service task|
| Cluster & Context Path| bb_securecardhandler_elk_cluster_nodes <br> bb_securecardhandler_context_path| variables to set ELK cluster nodes and context path|

<br>

## **Users_Mongo variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| Enabling Roles and Installing packages| util_filesystem_enable <br> mongofamily_server_security_enabled <br> util_filesystem_install_package_list <br> mongofamily_security_util_enabled| variables to enable the Util and mongofamily roles and install dependent packages|
| Users| mongofamily_security_users_details| variables to set database user profiles and roles|

<br>

## **ZW_Marketplace variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| ECS task definition| zw_marketplace_server_task_family_name <br> zw_marketplace_server_task_executionRoleArn <br> zw_marketplace_server_task_networkmode <br> zw_marketplace_server_task_ecsmode <br> zw_marketplace_server_task_cpu <br> zw_marketplace_server_task_memory <br> zw_marketplace_server_task_container_name <br> zw_marketplace_server_task_container_image <br> zw_marketplace_server_task_container_cpu <br> zw_marketplace_server_task_container_memory <br> zw_marketplace_server_task_container_credentials_parameter <br> zw_marketplace_server_task_container_essential| variables to define the ECS task definitions of the server|
| Environment| zw_marketplace_server_task_container_env <br> zw_marketplace_sidecar_server_task_container_essential <br> zw_marketplacenginx_server_task_container_env <br> zw_marketplace_server_task_container_mon_env <br> zw_marketplace_server_task_container_secretenv_definition|  Environmental variables of the ZW Marketplace server|
| Logging| zw_marketplace_server_task_container_log_driver <br> zw_marketplace_server_task_container_log_logsgroup <br> zw_marketplace_server_task_container_log_logsregion <br> zw_marketplace_server_task_container_log_logsprefix| variables to collect container logs|
| Loadbalancing| zw_marketplace_alb_arn <br> zw_marketplace_service_name <br> zw_marketplace_targetgroup_name <br> zw_marketplace_targetgroup_protocol <br> zw_marketplace_targetgroup_success_http_code <br> zw_marketplace_targetgroup_hc_interval <br> zw_marketplace_targetgroup_hc_timeout <br> zw_marketplace_targetgroup_hc_healthycount <br> zw_marketplace_targetgroup_hc_unhealthycount <br> zw_marketplace_targetgroup_hc_path <br> zw_marketplace_targetgroup_hc_protocol <br> zw_marketplace_targetgroup_targettype | variables to attach the server to a load balancer and configure health checks.|
| Autoscalling| zw_marketplace_service_count <br> zw_marketplace_service_platform_version <br> zw_marketplace_service_hc_graceperiod <br> zw_marketplace_service_autoscalling_policy_type <br> zw_marketplace_service_autoscalling_min_task <br> zw_marketplace_service_autoscalling_max_task <br> zw_marketplace_service_mem_autoscalling_policy_name <br> zw_marketplace_service_cpu_autoscalling_policy_name <br> zw_marketplace_service_mem_autoscalling_tracking_scaling_target_value <br> zw_marketplace_service_cpu_autoscalling_tracking_scaling_target_value <br> zw_marketplace_service_mem_autoscalling_tracking_scaling_metric_spec <br> zw_marketplace_service_cpu_autoscalling_tracking_scaling_metric_spec <br> zw_marketplace_service_mem_autoscalling_tracking_scalout_cooldown <br> zw_marketplace_service_mem_autoscalling_tracking_scalin_cooldown <br> zw_marketplace_service_cpu_autoscalling_tracking_scalout_cooldown <br> zw_marketplace_service_cpu_autoscalling_tracking_scalin_cooldown <br> zw_marketplace_service_awscli_enabled <br> zw_marketplace_service_scheduled_autoscalling| variables to define autoscalling for the zw marketplace task|
| Schedule| zw_marketplace_service_wake_cron <br> zw_marketplace_service_sleep_cron| variables to configure active and dormant time for the ZW market place's UAT servers|

<br>

## **ZwCellulant Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST setup| proxy_zwcellulant_vhost_file | variable definition to set virtual host|
| Proxy Upstream| zwcellulant_upstream_host1 <br> zwcellulant_upstream_host1_mon_type <br> zwcellulant_upstream_host1_mon_scheme <br> zwcellulant_upstream_host2 <br> zwcellulant_upstream_host2_mon_type <br> zwcellulant_upstream_host2_mon_scheme | proxy host upstream variable definition|
webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_install_details | variables to enable the webserverfamily role and to install webserver packages|
| Webserver configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variables to configure the proxy web server|
| Elasticbeats Setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variables to setup and configure elasticbeats to ship data|

<br>

## **ZwStanbic Proxy variables**
| section| variable definition | description |
| :------| :-------------------| :-----------|
| VHOST Setup| proxy_zwstanbic_vhost_file| variable definition to set virtual host|
| Proxy Upstream| zwstanbic_upstream_host1 <br> zwstanbic_upstream_host1_mon_type <br> zwstanbic_upstream_host1_mon_scheme <br> zwstanbic_upstream_host2 <br> zwstanbic_upstream_host2_mon_type <br> zwstanbic_upstream_host2_mon_scheme <br> zwstanbic_upstream_host3 <br> zwstanbic_upstream_host3_mon_type <br> zwstanbic_upstream_host3_mon_scheme <br> zwstanbic_upstream_host4_mon_type <br> zwstanbic_upstream_host4_mon_scheme | proxy host upstream variable definitions|
| Enabling webserver roles and installing webserver packages| webserverfamily_nginx_ppa_version_enable <br> webserverfamily_nginx_enable <br> webserverfamily_nginx_common_validation_enable <br> webserverfamily_nginx_common_restart_enabled <br> webserverfamily_nginx_install_details| variables to enable webserver roles and to install webserver packages|
| Webserver Configuration| webserverfamily_nginx_push_configfiles_details <br> webserverfamily_nginx_deletefiles_details <br> webserverfamily_nginx_common_enable_sites_details_hash | variables to configure the proxy web server|
| Elasticbeats setup| elasticbeats_configuration_details <br> elasticbeats_systemd_details <br> elk_instance_name| variables to setup and configure elasticbeats to ship data|