# Self-hosted Applications

This repository provides Ansible playbooks for deploying various self-hosted applications using **Podman**, **Caddy**, and **Firewalld**.

Before getting started, make sure to set up the required environmental variables by exporting them from the `.secrets` file.

## Getting started
1. Clone this repository to your local machine:
	`git clone https://github.com/your-username/self-hosted.git`

2. Navigate to the repository directory:
	`cd self-hosted-apps`

3. Copy the `.secrets.example` file and update it with your actual secrets:
	`cp .secrets.example .secrets`

	Edit the .secrets file to contain your specific environmental variables.

4. Export the secrets:
    `export $(grep -v '^#' .secrets | xargs)`

## Installation

To install a specific self-hosted application, run the `create.yml` playbook located in the corresponding subfolder within `./containers`. This playbook configures the system and copies all the required files for the application.

Example:

`ansible-playbook -i username@127.0.0.1, ./containers/app-name/create.yml`

Replace `app-name` with the specific application you want to install.

## Removal

To remove a self-hosted application, run the `destroy.yml` playbook located in the corresponding subfolder within ./containers.

This playbook removes any Podman, Systemd, Caddy, and Firewalld configurations related to the application.

`ansible-playbook -i username@127.0.0.1, ./containers/app-name/destroy.yml`

Replace app-name with the specific application you want to remove.

## Notes

- Make sure to review and customize the `.secrets.example` file before exporting the secrets.
- Keep your secrets secure and never share the `.secrets` file.

Happy self-hosting! 🚀
