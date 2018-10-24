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

Create
```bash
mkdir -p ~/dhis2_home
touch ~/dhis2_home/config.js
```

add contents to `config.js`
```
module.exports = {
    "baseUrl": "http://192.168.22.11:8080/dhis",
    "authorization": "Basic YWRtaW46ZGlzdHJpY3Q="
}
```

add env. variable `DHIS2_HOME` to `~/.zshrc`

```js
export DHIS2_HOME='/usr/home/${USERNAME}/dhis2_home'
```
