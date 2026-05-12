# Lab Title: Basic Web CTF Walkthrough with Gobuster and Enumeration

## Goal:
To capture all 3 flags

## Platform:
TryHackMe / VulnHub / Local VM

---

## Step 1: Start the Lab and Get the Target IP

# Read the full lab description carefully.
# Start the target machine and note the IP address provided.

---

## Step 2: Scan the Target with Nmap

nmap -sS -PA <target-ip>

# Check if common ports like 80, 443, or 8080 are open.

---

## Step 3: Directory Enumeration using Gobuster

gobuster dir -u http://<target-ip> -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt -x php,txt,html -t 50

# Look for hidden directories like /files, /secret, etc.

---

## Step 4: Inspect Discovered Files or Directories

# Example:
# If /files is discovered, visit it in your browser:
firefox http://<target-ip>/files

# Explore each file one by one. Look for:
# - A file can have username(in source code)
# - A file can have password
# - A file that is a login page

---

## Step 5: Login with Credentials

# Use the gathered username and password to login.
# Example login page: http://<target-ip>/login.php

---

## Step 6: Command Interface Enumeration

# After successful login, if it opens a shell interface:

# List directories
ls

# Explore directories recursively
# Use tools like:
# - less
# - more
# - cat

less Sup3rs3cretpickl3Ingred.txt
ls /home
ls /home/rick
less /home/rick/"second ingredients"
sudo ls /root/
sudo less/root/3rd.txt



---

## Step 7: Capture Flags

# Copy and store the content of any flag files:

---

## Completion

# Note down all flags found.
# Mark the lab as complete on the platform.
