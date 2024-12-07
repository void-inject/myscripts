# Automation Scripts & Utilities

This repository contains a collection of scripts designed for various automation tasks and general utilities. The scripts are intended to help automate repetitive tasks, improve workflow, and simplify day-to-day operations.

## Table of Contents

- [Overview](#overview)
- [Requirements](#requirements)
- [Setup](#setup)
- [Scripts](#scripts)
    - [Log-Recorder.sh](#log-recordersh)
    - [IP-Scoper.sh](#ip-scopersh)
    - [git-pusher.sh](#git-pushersh)
    - [GMAIL-alerts.sh](#gmail-alertssh)
    - [Telegram-alerts.sh](#telegram-alertssh)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Overview

This repository provides several automation scripts that can be used in various environments, including Linux systems. These scripts are written in **Bash** and are designed for tasks such as Git management, system maintenance, and process automation.

## Requirements

Before using the scripts, ensure the following dependencies are installed:

- **Bash**
- `arp-scan` (for `GMAIL-alerts.sh`)
- `sendemail` (for `GMAIL-alerts.sh`)
- `git` (for `git-pusher.sh`) 

## Setup

1. Clone the repository:
```bash
git https://github.com/void-inject/My_Automation_Scripts.git Automation_Scripts
cd Automation_Scripts
```

2. Make the scripts executable:
```bash
chmod +x *.sh
```

## Scripts

### Log-Recorder.sh

#### Description:

This Bash script is designed to create a logging mechanism for terminal sessions.

#### Usage:

```bash
./Log-Recorder.sh
```

---

### IP-Scoper.sh

#### Description:

This script has 3 use-cases:
1. generates a list of IP addresses for a specified target subnet and saves them to an output file. The output file is named in the format: `target-host.txt`, where _target_ is the given subnet (e.g., 192.168.1).
2. automates the process of checking the availability of IP addresses listed in a text file. It removes unreachable IP addresses from the file, leaving only the ones that are reachable.
3. you can use both functions at once.

#### Example Usage:

```bash
./IP-Scoper.sh -g 192.168.1 -s 192-168-1-host.txt
```

---

### git-pusher.sh

#### Description:

This Bash script automates the process of checking multiple Git repositories for uncommitted changes and keeping them up to date with the remote repository.

#### Usage:

```bash
./git-pusher.sh
```

---

### GMAIL-alerts.sh

#### Description:

This Bash script performs continuous ARP scans on a specified target network using `arp-scan`. It detects new hosts that are not already listed in a known hosts file and logs them in a separate file. If a new host is found, the script sends an email notification with the host's details. The script sleeps for a random time between scans to avoid excessive network usage.

#### Example Usage:

```bash
./GMAIL-alerts.sh 192.168.1.0/24 192-168-1-hosts.txt eth0
```

---

### Telegram-alerts.sh

#### Description:

This Bash script performs continuous ARP scans on a specified target network using `arp-scan`. It detects new hosts that are not already listed in a known hosts file and logs them in a separate file. If a new host is found, the script sends a Telegram notification with the host's details. The script sleeps for a random time between scans to avoid excessive network usage.

#### Example Usage:

```bash
./Telegram-alerts.sh 192.168.1.0/24 192-168-1-hosts.txt eth0
```

## Contributing

Contributions are welcome! If you'd like to contribute to this project, please fork the repository, make your changes, and create a pull request. Make sure to follow the guidelines for code quality and documentation.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
