# ansible-kube
1. adjust inventory/hosts.yaml
2. install required software
```
export ANSIBLE_HOST_KEY_CHECKING=False
ansible-playbook -i inventory/hosts.yaml playbooks/1-install_software.yaml
```
3. configure and run kubernetes
```
ansible-playbook -i inventory/hosts.yaml playbooks/2-configure_k8s.yaml
```
4. apply Contrail manifest
```
ansible-playbook -i inventory/hosts.yaml playbooks/2-create_manifest.yaml
```
5. logon to one of the master nodes
```
kubectl get pods -n contrail
```
6. reset when done
```
ansible-playbook -i inventory/myhost.yaml playbooks/4-reset.yaml
```
