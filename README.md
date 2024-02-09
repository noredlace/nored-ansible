# nored-ansible
Test Repo for Automated Deployment of Sprocket

Intention is a hardcoded Ansible Script for a Standard Setup and then Deployment of Sprocket

Work can be done to further allow this to be variable

As well as support Upgrades/SiteConfiguration Changes

# PreRequirements
Web and DB Server with C and D Drives
DB Server Installed with SQL Server 2022. No further Configuration

WinRM Scripts run to enable WinRM on both Web and DB Servers

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


