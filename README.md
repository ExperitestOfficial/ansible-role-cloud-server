Experitest - Cloud Server ansible role
=========

[![Build Status](https://travis-ci.org/ExperitestOfficial/ansible-role-cloud-server.svg)](https://travis-ci.org/ExperitestOfficial/ansible-role-cloud-server)

This role will install \ uninstall cloud server for windows, linux and mac os hosts

Requirements
------------

* [ansible-role-java8](https://github.com/ExperitestOfficial/ansible-role-java8) must be installed on all machines. <br>
* This role assumes that you have [postgresql server](https://github.com/ExperitestOfficial/ansible-role-postgresql-server) already installed. <br>
* Supports windows, linux and mac os hosts only.

Role Variables
--------------

| Name | Description |            Type            | Default | Required |
|------|-------------|:--------------------------:|:-----:|:-----:|
| state | should the application be present or absent |      present, absent       | present | no |
| app_version | application version to install |           string           | 12.12.7794 | no |
| server_port | port number for the server |           number           | 8080 | no |
| extra_application_properties | additional props to be override in application.properties file |            dict            | {} | no |
| extra_logback_properties | additional props to be override in logback.properties file |            dict            | {} | no |
| extra_xml_conf | extend xml configuration |            dict            | {} | no |
| extra_java_options | extand java options |      array of strings      | [] | no |
| license_type | license type | trial \ license4j \ spring | trial | no |
| license4j_file_content | license file content |           string           |  | when license_type is license4j |
| db_connection_string | connection string to postgres |           string           | jdbc:postgresql://localhost:5432/cloudserver | no |
| db_username | username for db connection |           string           | postgres | no |
| db_password | password for db connection |           string           |  | no |
| installation_root_folder | the root folder in which the application will be installed under cloudserver-{version} folder |           string           | for mac: /Applications/Experitest <br> for windows: C:\\Experitest <br> for linux: /opt/Experitest | no |
| java_version | java jre version to install |           string           | 8u292-b10 | no |
| custom_download_url | custom url to download the installation from (zip format) |           string           |  | no |
| custom_download_username | username to download from custom url on windows |           string           |  | no |
| custom_download_password | password to download from custom url on windows |           string           |  | no |
| start_after_install | should application start after installation is completed |          boolean           | True | no |
| clear_temp_folder | remove temp folder after installation |          boolean           | False | no |
| clear_before_install | removing old installation before installing new version |          boolean           | False | no |
| kill_notepad | kill notepad/notepadd++ apps on windows |          boolean           | False | no |
| cloud_backup_dir | the default path for the cloud backups |           string           | for mac: /Library/Application Support/Experitest/cloud-server <br> for windows: C:\\ProgramData\\cloud-server <br> for linux: /var/lib/Experitest/cloud-server | no |
| download | only download the release version |          boolean           | True | no |
| deploy | only deploy the release version |          boolean           | True | no |
Example Playbook
----------------
### [see working example](/example)
