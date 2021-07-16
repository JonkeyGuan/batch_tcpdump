yum -y install epel-release

yum -y install ansible 

yum -y install tcpdump

git clone https://github.com/JonkeyGuan/batch_tcpdump.git

cd batch_tcpdump

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa create-user.yaml 

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa copy-tcpdump.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa run-tcpdump.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa stop-tcpdump.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa gather-tcpdump-file.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa delete-tcpdump-file.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa delete-tcpdump.yaml

ansible-playbook -i hosts --key-file ~/.ssh/id_rsa delete-user.yaml 

