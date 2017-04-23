# Example Ansible SSH Keys by Hosts File

This simple playbook deploys the authorized_key file to the root user of a specific customer site. In this instance "Customer 1" or "Customer2"

In this example, "Customer 1" and "Customer 2" have different ansible hosts files which also contain the public_keys as variables

## Usage

Simply clone the repo and then spin up the included Vagrant boxes for "Customer 1" and "Customer 2" with `vagrant up`

Once the Vagrant Boxes are live they can be configured with the following commands:

- Customer 1
`ansible-playbook -i hosts_customer1 ssh.yml`
- Customer 2
`ansible-playbook -i hosts_customer1 ssh.yml`

To confirm this has worked as expected you can run the following commands:

- First, SSH into the _Customers_ VM
  - `vagrant ssh customer1`
- Then `sudo cat` the root users `authorized_key` file
  - `sudo cat /root/.ssh/authorized_key`

The above also applies to `vagrant ssh customer2` you should find that the `authorized_key` is different on each VM.

Once you're complete, simply destroy the environment with `vagrant destroy -f` (`-f` forces the destruction without prompting)
