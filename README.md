# Prerequistes

Install [Vagrant](https://www.vagrantup.com/downloads.html), [Ansible](http://docs.ansible.com/ansible/latest/intro_installation.html).

Download on of the demo data databases from here [https://github.com/dhis2/dhis2-demo-db](https://github.com/dhis2/dhis2-demo-db). Extract and rename .sql file to **demo.sql** and put it inside dhis-core-server below. Before running `vagrant up`


# Setup

```bash
$> git clone https://github.com/adeelshahid/dhis2-core-ansible.git dhis-core-server
$> cd dhis-core-server
$> vagrant plugin install vagrant-disksize
$> vagrant up
```


# View
When vagrant finishes with installation and provision. You can check here for DHIS2 admin [http://192.168.22.11:8080/dhis/](http://192.168.22.11:8080/dhis/)

**username:** admin, **password:** district

# Frontend Apps setup

Inside ~/dhis2_home create *config.json* file. This would be read by app to know where is the core dhis2-server located.

```json
{
    "baseUrl": "http://192.168.22.11:8080/dhis",
    "authorization": "Basic YWRtaW46ZGlzdHJpY3Q="
}
```
