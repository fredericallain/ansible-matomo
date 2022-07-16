# Use ansible to setup a Matomo instance

## before everyhting, make sure you have installed the required component

    ansible-galaxy collection install community.mysql 
    ansible-galaxy collection install community.general

## Update all varariables in group_vars/all.yml

    ansible_user: <USERNAME>
    ansible_email: <MAIL@DOMAIN.TLD>
    systemd_dir: /etc/systemd/system
    system_timezone: "Europe/Paris"
    mysql_root_pass: '' #Leave empty if it's a first install 
    new_mysql_root_pass: '<StrongPassword>'
    matomo_db_user: <USERNAME>
    matomo_db_password: '<StrongPassword>'
    matomo_table_prefix: <PREFIX>
    matomo_salt: "<StrongSalt>"
    matomo_admin_email: <MAIL@DOMAIN.TLD>
    matomo_url: <DOMAIN.TLD>

* Remember that you'll need to have an ssh key setup to access to your instance.

## Then use the command to start the setup
    ansible-playbook update.yml --ask-become

## After install is done, connect to the GUI using the url you've setup in all.yml
DOMAIN.TLD

### Have fun !