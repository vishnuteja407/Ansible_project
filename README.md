# Ansible_project

ansible-playbook playbook.yaml -i inventory.txt 

ansible-vault create myfile.yaml
ansible-vault view myfile.yaml
ansible-vault edit myfile.yaml
ansible-vault encrypt_string sublime-text

ansible-vault encrypt inventory.txt
ansible-vault view inventory.txt
ansible-vault decrypt inventory.txt
ansible target* -m ping -i inventory.txt --ask-vault-pass
ansible all --list-hosts
ansible-galaxy collection list


ansible-galaxy collection install cisco.nso
ansible-galaxy collection install ansible.posix
ansible-galaxy collection install community.general
ansible-playbook httpbytag.yaml -t i-httpd       - execute playbook based on tag
ansible-playbook httpbytag.yaml --list-tags 
ansible-playbook httpbytag.yaml —start-at-task “task name”

/etc/ansible/hosts
/etc/ansible/ansible.cfg
/etc/ansible/playbooks/
/etc/ansible/roles/


ansible-playbook changepass.yaml -i vmdetails.txt --extra-vars newpassword=abc123

ansible all -m file -a "path=/home/deployer/adhoc1 state=touch mode=700" -i vmdetails.txt 
ansible all -m file -a "path=/home/deployer/adhoc1 state=touch mode=700" -i vmdetails.txt 
ansible all -m file -a "path=/home/deployer/adhoc1 state=absent" -i vmdetails.txt 
ansible all -m copy -a "src=./data.csv dest=/home/deployer/data.csv" -i vmdetails.txt 
ansible all -m file -a "path=/home/deployer/data.csv state=absent" -i vmdetails.txt 
ansible all -m yum -a "name=telnet state=present" -i vmdetails.txt
ansible all -m service -a "name=httpd state=started" -i vmdetails.txt 
ansible all -m service -a "name=httpd state=started enabled”=yes -i vmdetails.txt   -> enable service at boot time
ansible all -m shell -a "systemctl status docker" -i vmdetails.txt
ansible all -m shell -a “yum remove httpd“ -i vmdetails.txt
ansible all -m user -a “name=jsmith home=/home/jsmith shell=/bin/bash state=present” -I vmdetails.txt
ansible all -m user -a “name=jsmith group=ifazal”
ansible all -m user -a “name=jsmith home=/home/jsmith shell=/bin/bash state=absent” -I vmdetails.txt
Ansible all -m shell -a “userdel jsmith”
Ansible all -m setup -> module to pull system info
Ansible client1 -a “/sbin/reboot”
ansible localhost -m setup
