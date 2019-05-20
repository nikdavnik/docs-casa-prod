# Gluu Casa Quick Start Guide

## Overview

Gluu Casa is a self-service web portal for end-users to manage security preferences for their account in a Gluu Server. Follow this guide to install and configure a basic Casa deployment.

## Prerequisites

Casa requires a server or virtual machine with at least the following minimum requirements:

| CPU Unit | RAM | Disk Space | Processor Type |
|------ | ---- | ---- | ---- |
| 2  | 5 GB | 40 GB | 64 Bit |

The following operating systems are supported:

- Ubuntu 14/16
- CentOS 6/7
- RHEL 6/7
- Debian 8/9

## Getting started

1. Install packages

    Casa requires an operational Gluu Server with a matching version number to be installed on the same server or virtual machine. Follow the [Casa installation instructions](./installation.md#installation-via-linux-packages) to install the packages. If you don't already have the Gluu Server installed, it will be automatically installed with Casa.
    
    Do not run setup_casa.py at this time.

1. Set up Gluu Server

    If setting up the Gluu Server for the first time with this installation, follow [these instructions](https://gluu.org/docs/ce/3.1.6/installation-guide/install/) to set up the newly installed package.

    If the machine already includes a Gluu Server that was set up with at least the following components, you can skip this step:

      - oxAuth OAuth2 Server
      - oxTrust GUI
      - Gluu LDAP (such as OpenDJ)
      - Apache
  
1. Set up Casa

    Once the Gluu Server is set up, follow [these instructions](./installation.md#run-the-setup-script) to set up Casa. 

    oxd is required to integrate Casa with the Gluu Server. When asked if the server has oxd installed, select `no` and allow the script to install it.

1. Enable authentication scripts

    Log in to oxTrust as an administrator and follow [these instructions](./admin-console.md#enabled-methods) to enable the desired 2FA credentials to be managed with Casa.

1. Test enrollment and 2FA

    - [Enroll](../user-guide.md#2fa-credential-details-enrollment) at least two credentials on a non-administrator user.

    - [Turn on](../user-guide.md#turn-2fa-onoff) 2FA for the account.

    - Test 2FA Authentication by logging off and logging back in. Application access should now require a second authentication factor.

1. Finish configuration

    Once satisfied with testing, configure the Gluu Server to log in users via Casa for all applications the server protects. Read the guide [here](./admin-console.md/#set-default-authentication-method-gluu).

1. Check out available plugins

    Browse our [catalog of plugins](https://casa.gluu.org/plugins) to add features and expand Casa!
