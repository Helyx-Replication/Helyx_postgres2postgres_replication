# Installation

### Overview
Helyx is distributed as an RPM package to simplify installation and management. By default, Helyx is installed in the directory /var/lib/helyx.

This section describes the steps to install Helyx from a standard YUM/DNF repository as well as from a local repository if you download the RPM manually.

### Prerequisites
Operating System: Linux (RHEL, CentOS, Rocky Linux, Oracle Linux, Fedora, etc.).
Privileges: Root or sudo access.
Package Manager: yum or dnf depending on your OS version.
Network Access (for online installation): Access to the configured YUM repository

### Installing Helyx from a Local Repository

Create Local Repository Directory :
```ruby
mkdir -p /opt/localrepo/helyx
```
```ruby
cp helyx-1.1.0.rpm /opt/localrepo/helyx/
```
Create Repository Metadata :
```
cd /opt/localrepo/helyx
```
```
createrepo .
```
Add Local Repository Entry (create /etc/yum.repos.d/helyx-local.repo):
```ruby
[helyx-local]
name=Helyx Local Repository
baseurl=file:///opt/localrepo/helyx
enabled=1
gpgcheck=0
Install from Local Repository:
```
```ruby
sudo yum install helyx -y
```
Post installation verifies and ensures binaries are installed under **/var/lib/helyx** location.