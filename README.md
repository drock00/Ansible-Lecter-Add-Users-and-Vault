# Ansible-Lecter-Add-Users-and-Vault

### Create users, groups, set passwords using vault, and enable ssh control.

Add users and groups to managed nodes using loop construct in a variable file. Password, password, password. There's a vault file 'sec.yml' that can be accessed by entering the password 'password' The variable inside contains a password to be set on the users. Wanna guess what it is? If you guessed 'password' then you'd be correct. After setting the password on the users, the shell module checks to see if all the users are in group wheel, if so then the play succeeds. Otherwise the play fails. Unless you feel like tampering, this play will succeed. 


# Example Run 1
```sh
$ ansible-playbook add_users.yml 
```

# Validate using adhoc

```sh
$ ansible-playbook ansible22.example.com -m shell -a "cat /etc/passwd | grep wheel"
```

### Tech and Running the file

Bin, Bash, Boom. You should probably be setting up a lab of virtual hosts to try out your plays. You will have to adjust the inventory file accordingly and of course your /etc/hosts or whatever DNS resolution you are using. 