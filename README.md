This repository documents the implementation of a small-scale Zero Trust architecture using free tools. The project explores key principles like network segmentation, access control, continuous monitoring, and least privilege.

To follow each step, view the attached .txt files for code lines

The project aims to establish a secure environment where trust is not inherently granted. This is achieved by:

**Network Segmentation**: The environment is divided into separate networks using Docker containers, creating boundaries and limiting direct communication.
**Access Control**: SSH key-based authentication replaces password authentication, and IP-based access controls using UFW (uncomplicated firewall) restrict access to specific IP addresses.
**Continuous Monitoring**: Syslog-ng is configured to capture SSH login attempts for monitoring and analysis.
**Least Privilege**: The focus is on granting only the minimum permissions necessary for users and applications to perform their tasks.

**Resources:**

_Prerequisites_:

Windows Server 2022 with access(Accessed through ASU Cyber Lab VM)
Docker Desktop installed on Windows Server 2022 (https://www.docker.com/products/docker-desktop/)
Basic understanding of command line tools and networking concepts

**Steps:**

_Environment Setup_:

Pull the Ubuntu image using Docker.
Create a dedicated Docker network for segmentation.
Deploy and start an Ubuntu server container attached to the network.
Install essential tools on the container (OpenSSH, iptables, syslog-ng).

_Access Control Configuration_:
Generate SSH keys on the Windows Server and transfer the public key to the Ubuntu container.
Set permissions to restrict access.
Optionally adjust SSH configuration in the container (e.g., disable password authentication).
Test SSH access using the key.
Implement IP-based access controls with UFW, allowing SSH access only from the Windows Server IP address.

_Logging and Monitoring Setup_:
Configure Syslog-ng in the container to capture SSH login attempts.
Attempt successful and unsuccessful logins to generate log entries.
View the logs using tail -f /var/log/ssh.log.

**Further Exploration**:

Research advanced Zero Trust architectures and concepts.
Explore additional security tools and techniques applicable to Zero Trust principles.
Consider incorporating intrusion detection and prevention systems (IDS/IPS) for comprehensive monitoring.
Feel free to contribute or raise issues with this project!
