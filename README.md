# nored-ansible
Test Repo for Automated Deployment of Sprocket

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


