# Dataverse Development Playbook

Run this Ansible playbook locally on a mac to setup a development Dataverse instance.

Everything is installed and run in the user's space, no root access required. The idea here is to get the project running locally, no matter what it takes. 

This playbook provides a way of setting Dataverse up in "development mode" -- making code changes and seeing them work, or not. This is different from the "bundle everything up for deployment mode." If you are interested in using Ansible for regular deployment, see: [Ansible role for installing and maintaining Dataverse] (https://github.com/IQSS/dataverse-ansible)

## Installation

  1. Clone this repository to your local drive.
  2. [Install Ansible](http://docs.ansible.com/intro_installation.html)<sup>&dagger;</sup>.
  3. [Install Homebrew] (http://brew.sh/).
  4. Run `ansible-playbook main.yml --tags "install"` from the same directory as this README file.
  5. Run `ansible-playbook main.yml --tags "start"` to launch postgresql, solr and glassfish.
  6. Deploy your Dataverse war file.
  7. Login as dataverseAdmin and publish the root dataverse.
   
  
&dagger; _Ansible install docs say: "Readers that use virtualenv can also install Ansible under virtualenv, though we’d recommend to not worry about it and just install Ansible globally. Do not use easy_install to install ansible directly."_

## Ansible tag options

  - Remove all components: _clean_
  - Remove components: _pg-clean_, _solr-clean_, _glassfish-clean_
  - Install components: _pg-install_, _solr-install_, _glassfish-install_
  - Start components: _pg-start_, _solr-start_, _glassfish-start_
  - Stop components: _pg-stop_, _solr-stop_, _glassfish-stop_

## How to start and stop components without using Ansible

All components can be controlled via launchctl

  - Glassfish: `launchctl start glassfish` and `launchctl stop glassfish`
  - Solr: `launchctl start solr` and `launchctl stop solr`
  - Postgresql: `launchctl start postgresql` and `launchctl stop postgresql`
  
Glassfish can be controlled via asadmin as well

  - `/usr/local/glassfish4/glassfish/bin/asadmin start-domain domain1`
  - `/usr/local/glassfish4/glassfish/bin/asadmin stop-domain domain1`
   
## Applications installed

  - postgresql (9.3 via Homebrew)
  - solr 4.6.0
  - glassfish 4.1
  - jq (latest via Homebrew)
  
  


