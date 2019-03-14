## Ansible Wordpress Role

### What does the role do

Sets up Wordpress with LAMP on RedHat- and Debian-based systems. 

**NOTE:** I have not yet fully implemented the Debian part, wait for a future commit. Works seamlessly on RHEL and CentOS (sample run below).

### How to use it

The role is generally ready to use, just need to define your values at *vars/vars.yaml*, and if desired create another variable file called *secret.yaml* (used to contain sensitive variables such as passwords), prefferably using ansible-vault. Otherwise just input the variables in the *vars.yaml* file and delete any references to the *secret.yaml* variable file from tasks/*.

The *secret.yaml* file should contain the following variables:

- mysql_root_pass
- wordpress_user_pass

**NOTE:** Don't forget to include **become: yes** at your playbook otherwise you'll stumble upon permission errors.

###### ansible-vault help

```bash
ansible-vault create secret.yaml #will initiate dialog asking for password
ansible-vault edit secret.yaml #will ask for password and allow you to edit the file

```

### Sample Playbook run

[Here](https://asciinema.org/a/yf7UnOgBUVQR62U4zNXlSEbqI)