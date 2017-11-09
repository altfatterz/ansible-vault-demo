
```bash
export VAULT_PASSWORD=<password>
```	


```bash
ansible -m debug -a 'var=hostvars[inventory_hostname]' database
```

```json
localhost | SUCCESS => {
    "hostvars[inventory_hostname]": {
        "ansible_check_mode": false,
        "ansible_connection": "local",
        "ansible_playbook_python": "/usr/local/Cellar/ansible/2.4.1.0/libexec/bin/python2.7",
        "ansible_version": {
            "full": "2.4.1.0",
            "major": 2,
            "minor": 4,
            "revision": 1,
            "string": "2.4.1.0"
        },
        "group_names": [
            "database"
        ],
        "groups": {
            "all": [
                "localhost"
            ],
            "database": [
                "localhost"
            ],
            "ungrouped": []
        },
        "inventory_dir": "/Users/zoal/projects/study-vagrant-and-ansible/ansible-vault-demo",
        "inventory_file": "/Users/zoal/projects/study-vagrant-and-ansible/ansible-vault-demo/hosts",
        "inventory_hostname": "localhost",
        "inventory_hostname_short": "localhost",
        "mysql_host": "10.0.0.3",
        "mysql_password": "supersecretpassword",
        "mysql_port": 3306,
        "mysql_user": "fred",
        "omit": "__omit_place_holder__d320cc22092cfc72179f0d239500d3f1cc13a963",
        "playbook_dir": "/Users/zoal/projects/study-vagrant-and-ansible/ansible-vault-demo"
    }
}
```


```bash
⇒  ansible-playbook my_playbook.yml

PLAY [database] **********************************************************************************************************************************************************************************

TASK [Gathering Facts] ***************************************************************************************************************************************************************************
ok: [localhost]

TASK [print out group variables] *****************************************************************************************************************************************************************
ok: [localhost] => {
    "msg": "3306 and supersecretpassword"
}

PLAY RECAP ***************************************************************************************************************************************************************************************
localhost                  : ok=2    changed=0    unreachable=0    failed=0
```