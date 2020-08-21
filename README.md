[![Build Status](https://travis-ci.com/enr0s/ansible-role-k8s.svg?branch=master)](https://travis-ci.com/enr0s/ansible-role-k8s)
[![quality](https://img.shields.io/ansible/quality/49706)](https://galaxy.ansible.com/enr0s/ansible-role-k8s)
![LICENSE](https://img.shields.io/github/license/enr0s/ansible-role-k8s)

Ansible Role K8S
=========

Install k8s on your Raspberry (64 bit architecture).


Role Variables
--------------

Kubernetes packages to be installed on the server.
```
prerequisite_packages:
  - apt-transport-https
  - ca-certificates
  - python3-pip
kubernetes_packages:
  - kubelet
  - kubeadm
  - kubectl
python3_modules:
  - openshift
  - kubernetes
```
The minor version of Kubernetes to install and extra arguments to pass to kubelet during startup.
```
kubernetes_version: "1.18"
kubernetes_version_kubeadm: 'stable-{{ kubernetes_version }}'
kubernetes_kubelet_extra_args: ""
kubernetes_kubeadm_init_extra_opts: ""
kubernetes_join_command_extra_opts: ""
kubernetes_allow_pods_on_master: false
kubernetes_apiserver_advertise_address: ''
kubernetes_ignore_preflight_errors: 'all'
```
This role currently supports only flannel.
```
kubernetes_flannel_manifest_file: https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
kubernetes_pod_network:
  cni: 'flannel'
  cidr: '10.244.0.0/16'
```
Enable the Kubernetes web dashboard UI 
```  
kubernetes_enable_web_ui: true
kubernetes_web_ui_manifest_file: https://raw.githubusercontent.com/kubernetes/dashboard/v2.0.0/aio/deploy/recommended.yaml
```

Dependencies
------------

```
ansible-galaxy install -r molecule/default/requirements.yml
```

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```
  ---
  - hosts: all
    roles:
      - { role: ansible-role-k8s }
```

License
-------

Apache-2.0


Author Information
------------------

[https://blog.enros.me]
