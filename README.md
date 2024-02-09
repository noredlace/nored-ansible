# nored-ansible
Test Repo for Automated Deployment of Sprocket

Intention is a hardcoded Ansible Script for a Standard Setup and then Deployment of Sprocket

Work can be done to further allow this to be variable

As well as support Upgrades/SiteConfiguration Changes

# PreRequirements

* Web Server
  * C and D Drives
  * WinRM.ps1 Scripts Ran for WinRM Listener

* DB Server
  * C and D Drives
  * .Net Framework 4.7.2
  * SQL Server 2022
  * SQL Server Studio Management 2019 

Assumption is the above are the states that we will receive the Servers in. 

I expect this is automated on Deployment of VMs, but the only goal in this is to deploy a Sprocket Website

# Test Ping
```ansible all -i hosts.yml -m win_ping```

# Run the Entire Thing in One Go
```ansible-playbook -i hosts.ywml runAll.yml```

# Setup Sprocket Web Server
```ansible-playbook -i hosts.yml setupSprocketWeb.yml``` 

* Performs the following:
 * Installs IIS
 * Sets up preferred folder structure
 * addres entries in the HostFile 

# Setup Sprocket DB Server
```ansible-playbook -i hosts.yml setupSprocketDB.yml``` 

* Performs the following:
 * Sets up preferred folder structure
 * Installs SQLPackage
 * Add Firewall Inbound Rule for SQL Port 1433
 * Creates SQL Login
 * Set Default Directories of SQL Server
 * Enable TCP and NamedPipes on SQL Server
 
# Install Sprocket Web Files
```ansible-playbook -i hosts.yml installSprocketWeb.yml``` 

* Performs the following:
 * Copies the Sprocket Web Folder over
 * Copies the Sprocket Hangfire Folder over
 * Removes Default IIS Site/AppPool
 * Configures IIS Site Node's Web.Config for SQL Connection

TODO: Configure Sprocket Hangfire exe.Config modifications. Install as Service

# Install Sprocket DB Files
```ansible-playbook -i hosts.yml installSprocketDB.yml``` 
* Performs the following:
 * Copies backup *.bak file over
 * Restores the backup to a Database
 * Update Table SiteConfigurations

