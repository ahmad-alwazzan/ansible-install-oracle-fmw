This is a cloned repository, plan is to take Stevaras work and make it work on installing fmw 12.2.1.4
=================

Weblogic Ansible Playbook
=========================

## Detailed info

An Ansible Playbook (weblogic-fmw-domain.yml) to install and configure a WebLogic Server 12c with 
Oracle Fusion Middleware software for hosting Oracle Fusion Middleware (for example ADF) applications in Redhat Linux 7 (RHEL/CentOS/Oracle Linux) system.
This playbook is for version 12.2.1.3 of WebLogic and Fusion Middleware Infrastructure software.

Requirements for running the playbook:
- Configure your environment variables in infra-vars.yml. 
- Set your passwords in secrets.yml.
- A running Oracle Database for hosting the repositories is required and sys user password for generates the repositories.
- A running RHEL 7 system with minimal installation with network configured. (IP address, hostname etc).
- Download the latest Java 8 jdk and put the file in roles/linux-jdk/files and configure infra-vars.yml with that file name.
- Download the 12.2.1.3 Oracle Fusion Middleware installer from Oracle support and put it in roles/fmw-software/files

The playbook includes the following Ansible Roles:
- linux-wls: Configures the linux system with required packages, kernel settings etc.
- linux-jdk: Installs Oracle JDK 8.
- fmw-software: Installs Oracle Fusion Middleware Infrastructure software.
- fmw-domain: Creates a Domain with Fusion Middleware support (Enterprise Manager, JRF, etc).
- fmw-managed-server: Creates a managed server for host applications.

When the playbook finishes execution you can connect to weblogic server using wls12c1.private:7001/console.

## Licence

Forked project. Copyright (c) 2018 Stavros Kalapothas (aka Stevaras) <stavros@ubinet.gr>.
It is free software, and may be redistributed under the terms of the GNU Licence.
