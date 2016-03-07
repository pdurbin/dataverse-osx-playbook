# Dataverse Development Playbook

Run this Ansible playbook locally on a mac to setup a development Dataverse instance.

Everything is installed and run in the user's space, no root access required.

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

  - Remove components: _pg-clean_, _solr-clean_, _glassfish-clean_
  - Install components: _pg-install_, _solr-install_, _glassfish-install_
  - Start components: _pg-start_, _solr-start_, _glassfish-start_
  - Stop components: _pg-stop_, _solr-stop_, _glassfish-stop_

## How to start and stop components without using Ansible

All components can be controlled via launchctl (with the exception of stopping Glassfish)

  - Start Glassfish: `launchctl start glassfish` or `/usr/local/glassfish4/glassfish/bin/asadmin start-domain domain1`
  - Stop Glassfish: `/usr/local/glassfish4/glassfish/bin/asadmin stop-domain domain1`
  - Start/Stop Solr: `launchctl start solr` and `launchctl stop solr`
  - Start/Stop Postgresql: `launchctl start postgresql` and `launchctl stop postgresql`
   
## Applications

  - postgresql (latest via Homebrew)
  - solr 4.6.0
  - glassfish 4.1
  - jq (latest via Homebrew)
  
  


