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


## 1. Anisble Server /etc/host 등록
192.168.100.33 mysql1
192.168.100.23 mysql2
192.168.100.21 manager


## 2. ansible hsots 등록
vim /etc/ansible/hosts
[dbservers]
mysql1
mysql2
manager


## 3. git clone
git clone https://github.com/dkwlfowh/Ansible_Maria_MHA.git


## 4. ansible 서버에서 target 서버로 key 접속되도록
[root@ansible maria]# cd /etc/ansible/roles/maria


[root@ansible maria]# ansible-playbook key.yml -k root


[root@ansible maria]# ansible dbservers -m ping


## 5.MHA 설치
[root@ansible maria]# ansible-playbook install_db.yml

