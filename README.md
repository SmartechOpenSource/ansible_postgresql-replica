🐬 Ansible Playbook: PostgreSQL Installation with Replica 🐬

This Ansible playbook automates the installation of PostgreSQL and sets up a replica for high availability.

## Requirements
- Ansible installed on the control machine.
- SSH access to target machines.
- Internet connectivity on target machines for package installation.
## Usage
1. **Clone this repository:**
```
git clone https://github.com/SmartechOpenSource/ansible-postgresql-replica.git
cd ansible-postgresql-replica
```
2. **Update the inventory.ini file:** 
- here we need 2 or more IP addresses for the master and replica server.

3. **Edit the Vars file** 
- Edit the Vars/main.yml file with customized variables.

```
- postgres_version: PostgreSQL version to install (e.g., "12", "13", etc.).
- primary_server_ip: IP address of the master (primary) server.
- replica_ip: IP address of the replica server.
- name: PostgreSQL username that you want to create.
- password: Password for the PostgreSQL user.
- data_mount_path: Path to the PostgreSQL data directory.
- replication_user: "Username for connect to DB (Username that set in users.name)"
- replication_user_password: "Password for connect to DB (password that set users.password)"
- replication_db: "DB name for the connection (Default is Postgres)"

```
4. **Run the playbook and wait for the cluster init confirmation**

```
ansible-playbook -i inventory.ini main.yml

```