<p align="center">
  Google Cloud Create Simple GCP GCE VM Instance
</p>

## Step-01: Introduction
In this section, we will cover the following topics:
- Creating a Linux Virtual Machine (VM) instance in Google Cloud Platform (GCP).
- Connecting to the Linux VM instance using SSH via the GCP Console (Browser-based SSH).
- Exploring the configuration options and settings available in Browser-based SSH.
- Installing and configuring a basic web server on the VM instance, and accessing hosted web pages through the VM’s External IP address.


## Step-02: Create VM Instance
- Enable `Google Compute Engine API`
- Go to Virtual Machines -> VM Instances -> Create Instance -> New VM Instance -> Provide the required details
- **Name:** Ania-1-vm
- **Region:** us-central1
- **Zone:** Any
- **Machine Configuration:** 
  - **Series:** E2
  - **Machine Type:** e2-micro
- **Firewall**
  - Allow HTTP Traffic
- **Advanced Options:** We will learn these later in detail, lot to discuss for each and every option 
- Click on **Create**
  

## Step-03: Overview of the Newly Created VM
1. VM Filters: Used to quickly search, organize, and manage VM instances based on labels, status, or other attributes.
2. VM Internal IP: A private IP address assigned to the VM for communication within the GCP VPC network; not accessible from the public internet.
3. VM External IP: A public IP address assigned to the VM, allowing access from outside the GCP network (e.g., web browser or external client).
4. Connect to Linux VM: Access can be established using SSH via the GCP Console (browser-based SSH), Cloud SDK (gcloud compute ssh), or third-party SSH clients.


## Step-04: Connect to Linux VM Instance using SSH
1. Go to VM Instances -> Ania-1-vm -> SSH -> Open in browser window
2. Understand what happens in the background when establishing an SSH connection via the browser


## Step-05: Review wgrywka.sh
- Create a simple script named `wgrywka.sh` and put the below contnent and run it 
- **wgrywka.sh**
```t
#!/bin/bash
sudo apt install -y telnet
sudo apt install -y nginx
sudo systemctl enable nginx
sudo chmod -R 755 /var/www/html
HOSTNAME=$(hostname)
sudo echo "<!DOCTYPE html> <html> <body style='background-color:rgb(211, 211, 211);'> <h1>Super, ze mozemy sie razem uczyc! </h1> <p><strong>VM Hostname:</strong> $HOSTNAME</p> <p><strong>VM IP Address:</strong> $(hostname -I)</p> <p><strong>Application Version:</strong> V1</p> <p>Pozdrawiam, Ania</p> </body></html>" | sudo tee /var/www/html/index.html
```


## Step-06: Explore SSH Settings when connected via Browser
1. Instance Details – view metadata, configuration, and networking information of the connected VM instance.
2. Open New Connection – start an additional SSH session to the same or a different VM.
3. Change Linux Username – update the username used for the SSH session.
4. Upload File – transfer files from the local machine to the VM instance.
5. Download File – retrieve files from the VM instance to the local machine.
6. Copy & Paste Settings – configure how text is copied from and pasted into the SSH terminal.
7. Font Settings – adjust the font style used in the terminal.

## Step-07: Explore this section with short demo on YT
[Watch this](https://www.youtube.com/watch?v=L1ZvRPdOIi8)
