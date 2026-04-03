### phase3
기존 site_ansible.yml에 모여있던 구성 파일을 각 역할에 맞게 나눠 구성
ansible-playbook site.yml
ansible-playbook site.yml --syntax-check
ansible-playbook site.yml --tags helm -v 


### 디렉토리 구조
```
ansible
├── ansible.cfg
├── inventories
│   └── dev
│       ├── group_vars
│       │   └── all.yml
│       └── hosts.ini
├── roles
│   ├── argocd
│   │   ├── tasks
│   │   │   ├── deploy.yml
│   │   │   ├── kubeconfig.yml
│   │   │   ├── main.yml
│   │   │   └── verify.yml
│   │   └── templates
│   │       └── argocd-values.yaml.j2
│   ├── base
│   │   └── tasks
│   │       └── main.yml
│   ├── helm
│   │   └── task
│   │       └── main.yml
│   ├── k3s_firewall
│   │   └── tasks
│   │       └── main.yml
│   ├── k3s_master
│   │   └── tasks
│   │       ├── install.yml
│   │       ├── kubeconfig.yml
│   │       └── main.yml
│   ├── k3s_worker
│   │   └── tasks
│   │       └── main.yml
│   ├── nfs_server
│   │   ├── handler
│   │   │   └── main.yml
│   │   └── tasks
│   │       ├── configure.yml
│   │       ├── install.yml
│   │       ├── main.yml
│   │       └── service.yml
│   └── postgresql
│       ├── handler
│       │   └── main.yml
│       └── tasks
│           ├── configure.yml
│           ├── install.yml
│           ├── main.yml
│           └── service.yml
└── site.yml
```