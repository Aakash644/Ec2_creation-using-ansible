# Ansible Role for EC2 Creation with Ansible Vault

This Ansible role automates the creation of EC2 instances on AWS using Ansible, leveraging Ansible Vault for securely managing sensitive information such as AWS credentials.

## Prerequisites

Before using this role, ensure the following prerequisites are met:

- Ansible is installed on your local machine or Ansible control node.
- AWS CLI is installed and configured with access credentials (access key and secret key).
- Ansible Vault is set up to encrypt sensitive data (e.g., AWS credentials) securely.

## Installation

Clone this repository to your Ansible project or include it as a submodule:

```bash
git clone https://github.com/your-username/ansible-ec2-creation-role.git roles/ec2_creation
```

## Setup Vault 

1. **Create a password for vault**:

```
openssl rand -base64 2048 > vault.pass
```

2. **Add your AWS credentials using the below vault command**:

```
ansible-vault create group_vars/all/pass.yml --vault-password-file vault.pass
```
3. **Run the Playbook**: Execute your playbook using the `ansible-playbook` command, providing the Vault password when prompted:

   ```bash
   ansible-playbook -i inventory playbook.yml --ask-vault-pass
   ```

## Variables

- `aws_access_key`: AWS Access Key ID for authentication.
- `aws_secret_key`: AWS Secret Access Key for authentication.

**Note**: Ensure to keep your Vault password secure and manage access to the encrypted Vault file carefully.


## Acknowledgments

- Inspired by [Ansible Documentation](https://docs.ansible.com/)
