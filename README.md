# Dataverse OSX Development Ansible Playbook

Developers can run this playbook locally to setup a dataverse instance.

*See also*:

  - [Ansible role for installing and maintaining Dataverse] (https://github.com/IQSS/dataverse-ansible)

## Installation

  1. [Install Ansible](http://docs.ansible.com/intro_installation.html).
  2. [Install Homebrew] (http://brew.sh/).
  3. Clone this repository to your local drive.
  4. Run `ansible-playbook main.yml --tags "install"` from the same directory as this README file.

## Tag Options

## Included Applications / Configuration

Applications (installed with Homebrew):

  - postgresql
  - solr 4.6.0
  - glassfish 4.1
  - jq

### Things that still need to be done manually

  1. start glassfish: 
  2. start solr: launchctl start org.apache.solr
  2. deploy webapp
  3. publish root dataverse
  
## Testing the Playbook

## Author


