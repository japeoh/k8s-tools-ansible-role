# K8S Tools Ansible Role

Installs Kubernetes Development tools

*   [Kubectl](https://kubernetes.io/docs/reference/kubectl/overview/)
*   [Minikube](https://minikube.sigs.k8s.io/)
*   [Kops](https://kops.sigs.k8s.io/)

The tool(s) will be downloaded into folders created in the base directory and named _toolname-version_ e.g. _kubectl-1.18.0_

## Variables

| Variable              | Description                                        | Default Value
|-----------------------|----------------------------------------------------|---|
| k8s_tools_base_dir    | The tool specific directories will be created here | ~/tools
| k8s_tools_install_dir | The directory where the binaries will be installed | ~/bin


The specific version to be installed can be controlled by providing the version number and checksum.

| Variable                    | Default Value |
|-----------------------------|---|
| k8s_tools_kubectl_version   | 1.18.0
| k8s_tools_kubectl_checksum  | sha256:bb16739fcad964c197752200ff89d89aad7b118cb1de5725dc53fe924c40e3f7
| k8s_tools_minikube_version  | 0.9.2
| k8s_tools_minikube_checksum | sha256:3121f933bf8d608befb24628a045ce536658738c14618504ba46c92e656ea6b5
| k8s_tools_kops_version      | 1.16.0
| k8s_tools_kops_checksum     | sha256:dca9c93161d50d67f316e6e45ee86c2870bfeff0c5f07a10f8ae5bb847976a80

## Example Playbook

```yaml
- hosts: localhost
  become: yes
  roles:
    - japeoh.k8s_tools
      vars:
        k8s_tools_install_dir: /usr/local/bin
```
    
## License

GPLv3

##  Development

See [here](https://github.com/japeoh/ansible-role-development) for setup.
