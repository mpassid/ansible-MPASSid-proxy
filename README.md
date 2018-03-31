# Ansible scripts for installing MPASSid-proxy component
![](http://img.shields.io/:license-mit-blue.svg)

MPASS-proxy consists of several modules for Shibboleth Identity Provider v3, providing extensions for authentication, attribute resolution and audit logging.
For more information see <https://github.com/Digipalvelutehdas/MPASSid-proxy>


## Contribution

Developer information and more detailed documentation will be available in <http://www.mpass.fi> 

## Quick install guide
Currently ansible scripts only support single server installation. All the components are installed  in one server (shibboleth, httpd, MPASSid-proxy component) 
### Prerequisites

RedHat/CentOS 7 server (ie. virtual machine) with root privileges.
You can use the Vagrant configuration provided. 

### Installation steps
##### 1 Clone this  repository and use Vagrant to provision virtual server.

##### 2 Configuration parameters in ...roles/vars/secure.yml.

| Parameter | Description| 
|----------| -----------|
| app_root | Installation root |
| app_jetty | Jetty install path |
| app_shibbo | Shibboleth-IDP directory |
| app_jetty_base | Jetty base directory |
| mpassid_build | Temporary directory used during install |
| mpassid_data | Url for MPASSid data component |
| conf | Location for Shibboleth configuration |
| hash | Hash for encryption |
| entityID | Url for shibboleth |
| authn_flows | List of configured authentication flows|
| conf_authn | Location for authentication config |
| views | Location of configured views |    
| messages | Location of configured messages |
| flows_authn | Flows configuration directory |
| sp | Shibboleth SP configuration |


##### 3  Run Vagrant
`$ vagrant up `

If you prefer to use just the ansible scripts you can run them for example in localhost as follows: 

`$ sudo  ansible-playbook -i "localhost," -c local mpass-proxy.yml`


