# Ansible_Maria_MHA
Maria_10.2 MHA 구축 

Ansible을 이용해서 Cnet_OS Maria_10.2 MHA 를 구축한다. 원하는 다른 MariaDB 버전을 원한다면 /etc/ansible/roles/maria/templates/MariaDB.repo 수정하면 됨

### 순서
##### /etc/hosts
##### /etc/ansible/hosts
##### /etc/ansible/roles/maria/templates/mha.cnf
##### /etc/ansible/roles/maria/templates/master_vip_up.sh 
##### /etc/ansible/roles/maria/templates/slave_vip_up.sh
##### 파일들의 Hostname이 동일하게 되어있어야한다.

> 1. 압축해제



