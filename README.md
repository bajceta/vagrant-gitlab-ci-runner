# Gitlab CI Runner in Vagrant

Gitlab CI Docker runner in Vagrant. Provisioned by Ansible.

- author: Ondrej Sika <ondrej@ondrejsika.com>
- license: [MIT](https://ondrejsika.com/license/mit.txt)


## Install

Installation is super easy. Replace the variables with your config.

```
git clone git@github.com:ondrejsika/vagrant-gitlab-ci-runner.git
cd vagrant-gitlab-ci-runner
vagrant up --no-provision
url=https://gitlab.com/ci token=UwrYeazzUy1nD4aqtTfx name=shell-runner-vlada vagrant provision
```

OR

```
ansible-playbook -i hosts playbook.yml --extra-vars "url=https://gitlab.com/ci token=UwrYeazzUy1nD4aqtTfx name=shell-runner-vlada-run4"
ansible-playbook -i hosts playbook.yml --extra-vars "url=https://gitlab.trialbee.com/ci token=z3JabamVDQJNbeUxioWY name=vagrant-vlada"
gitlab-ci-multi-runner register --non-interactive --url https://gitlab.trialbee.com/ci --registration-token z3JabamVDQJNbeUxioWY --name vagrant-vlada-1 --tag-list '' --executor shell
```

