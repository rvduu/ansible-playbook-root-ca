# ansible-playbook-root-ca - create and install Root CA + server certificates allowing clients to use secure connections

This playbook creates a Root CA and server certificates for development purposes. It also ads the CA certificate to the list of trustes CA so that clients (`curl` and Firefox) can use a secure connection. For testing, this playbook also installs and enables a HTTPD server using the generated certificates.

## Prerequisite
* This playbook currently supports Red Hat family of distributions (RHEL/CentOS/Fedora)
* sudo access on the host
* Ansible Core
    ```
    sudo dnf install ansible-core
    ```


## Usage
* Update the `vars` section in the playbook to customize the certificate details
* Generate certificates and install them inclusing the HTTPD package on `localhost`
```
ansible-playbook --ask-become-pass ansible-playbook-root-ca.yml
```


## ToDo
* Create an Ansible role with example usage
* Add support for other Linux distributions

## Related information
* https://arminreiter.com/2022/01/create-your-own-certificate-authority-ca-using-openssl/
* https://github.com/gametize/ansible-role-install-root-cert
