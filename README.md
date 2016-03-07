# Dataverse Development Playbook

Developers can run this Ansible playbook locally to setup a dataverse instance.

*See also*:

  - [Ansible role for installing and maintaining Dataverse] (https://github.com/IQSS/dataverse-ansible)

## Installation

  1. [Install Ansible](http://docs.ansible.com/intro_installation.html).
  2. [Install Homebrew] (http://brew.sh/).
  3. Clone this repository to your local drive.
  4. Run `ansible-playbook main.yml --tags "install"` from the same directory as this README file.
  5. Run `ansible-playbook main.yml --tags "start"` to launch postgresql, solr and glassfish.
  6. Deploy your Dataverse war file.
  7. Login as dataverseAdmin and publish the root dataverse.

## Ansible tag options

  - Remove components: pg-clean, solr-clean, glassfish-clean
  - Install components: pg-install, solr-install, glassfish-install
  - Start components: pg-start, solr-start, glassfish-start
  - Stop components: pg-stop, solr-stop, glassfish-stop

### How to launch components withouth using Ansible

  - Start Glassfish: `launchctl start glassfish` or `/usr/local/glassfish4/glassfish/bin/asadmin start-domain domain1`
  - Stop Glassfish: `/usr/local/glassfish4/glassfish/bin/asadmin stop-domain domain1`
  - Start/Stop Solr: `launchctl start solr` and `launchctl stop solr`
  - Start/Stop Postgresql: `launchctl start postgresql` and `launchctl stop postgresql`
   
## Applications

  - postgresql (latest via Homebrew)
  - solr 4.6.0
  - glassfish 4.1
  - jq (latest via Homebrew)
  
  


