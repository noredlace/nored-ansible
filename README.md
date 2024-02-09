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

# Setup Sprocket DB Server
```ansible-playbook -i hosts.yml setupSprocketDB.yml``` 

# Install Sprocket Web Files
```ansible-playbook -i hosts.yml installSprocketWeb.yml``` 

# Install Sprocket DB Files
```ansible-playbook -i hosts.yml installSprocketDB.yml``` 


