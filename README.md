Kubernetes Kubelet Role
=========

[![Build Status](https://travis-ci.org/lucazz/ansible-k8s-kubelet.svg?branch=master)](https://travis-ci.org/lucazz/ansible-k8s-kubelet)

Simple Ansible role to installs and configures Kubelet

Requirements
------------

This role only requires Ansible version 1.9+

Role Variables
--------------

`k8s.version: 1.2.4`

`k8s.arch: amd64`

`k8s.skydns_address: {{ hostvars['k8s_master']['ansible_eth0']['ipv4']['address'] }}`

`k8s.master_address: {{ hostvars['k8s_master']['ansible_eth0']['ipv4']['address'] }}`

`k8sdomain: k8s-cluster.local`

`k8s.log_level: 0`

`kubelet.port: 10250`

Dependencies
------------

This role depends on the following roles:

*   [lucazz.etcd](https://github.com/lucazz/ansible-etcd)
*   [lucazz.calico](https://github.com/lucazz/ansible-calico)
*   [lucazz.k8s-master](https://github.com/lucazz/ansible-k8s-master)

Example Playbook
----------------

Using this roles as as simples as:
- hosts: k8s_master
  name: Gathering K8S Master Node facts
  tasks: []
- hosts: k8s_nodes
  roles:
    - lucazz.common
    - lucazz.etcd
    - lucazz.calico
    - lucazz.k8s-kubelet

License
-------
BSD

Author Information
------------------

Lucas do Amaral Saboya Works as Site Reliability Engineer @ [HE:labs](https://www.helabs.com)
