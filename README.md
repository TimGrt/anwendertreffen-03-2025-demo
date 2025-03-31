# Ansible Policy-as-Code demo

The content in this folder can be used to demo the *Ansible Policy-as-Code* [prototype implementation](https://github.com/ansible/ansible-policy) (Q1 2025), expect frequent changes to the project.

## How-to

Prepare your control node for the demo:

```console
ansible-playbook prepare-demo.yml
```

This will install *OpenPolicy* Agent and *ansible-policy*. Activate the Python VE:

```console
source demo-ve/bin/activate
```

## Conduct demo

Change into the demo folder:

```console
cd anwendertreffen-demo
```

Run *ansible-policy*:

```console
ansible-policy --project-dir . --policy-dir policies
```

> Currently (03-2025), there is a bug present in a utility-file. A [Pull Request](https://github.com/ansible/ansible-policy/pull/55) is open to fix this, still, if you encounter an error like ```ValueError: failed to run `opa eval` command``` with ```"message": "`if` keyword is required before function body"```, you'll need to fix this yourself until the pull request is merged.  
> Use the content of [this file](https://github.com/ansible/ansible-policy/blob/3df949758364f8e5fa510d2a3336c75739eacf3a/ansible_policy/rego/utils.rego) and paste it to `ansible_policy/ansible_policy/rego/utils.rego`.
