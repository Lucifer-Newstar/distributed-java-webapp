# Distributed Java Webapp with Vagrant

## Overview

This project is an educational learning initiative focused on setting up a distributed Java web application using Vagrant for server provisioning. It demonstrates the deployment of a multi-tier architecture consisting of a database server, caching layer, message queue, and application server, all orchestrated through virtual machines.

## Architecture

The setup includes the following components:

- **Database Server (db01)**: MySQL database running on CentOS Stream 9
- **Caching Server (mc01)**: Memcached for in-memory caching
- **Message Queue (rmq01)**: RabbitMQ for asynchronous messaging
- **Application Server (app01)**: Apache Tomcat with Java 17 for hosting the web application
- **Web Server (web01)**: Nginx on Ubuntu for load balancing and static content (manual provisioning only)

All servers are connected via a private network (192.168.56.0/24) and use hostmanager for DNS resolution.


## Features

- Automated provisioning using shell scripts
- Manual provisioning option for learning purposes
- Multi-tier distributed architecture
- Integration with MySQL, Memcached, RabbitMQ, and Elasticsearch
- Configurable application properties
- Host-based networking for inter-service communication

## Prerequisites

- [Vagrant](https://www.vagrantup.com/) (version 2.x)
- [VirtualBox](https://www.virtualbox.org/) or compatible virtualization provider
- At least 4GB RAM available for VMs
- Internet connection for downloading dependencies

## Installation and Setup

### Automated Provisioning

1. Navigate to the `vagrant/automated_provisioning/` directory:
   ```bash
   cd vagrant/automated_provisioning
   ```

2. Start the Vagrant environment:
   ```bash
   vagrant up
   ```

3. The provisioning scripts will automatically install and configure all services.

### Manual Provisioning

1. Navigate to the `vagrant/manual_provisioning/` directory:
   ```bash
   cd vagrant/manual_provisioning
   ```

2. Start the Vagrant environment:
   ```bash
   vagrant up
   ```

3. Manually configure each VM according to your learning objectives.

## Usage

After provisioning, you can:

- Access the application via the web server (if configured)
- Connect to individual services using their private IPs
- Modify `application.properties` to adjust service configurations
- Experiment with scaling, load balancing, and fault tolerance

## Configuration

Key configuration files:

- `application.properties`: Database, cache, and messaging settings
- `Vagrantfile`: VM definitions and network configuration
- Shell scripts in `automated_provisioning/`: Service installation and setup

## Learning Objectives

This project helps learners understand:

- Infrastructure as Code with Vagrant
- Distributed system architecture
- Service orchestration and dependencies
- Network configuration in virtual environments
- Java web application deployment
- Database and caching integration

## Contributing

This is an educational project. Feel free to:

- Add more services or VMs
- Improve provisioning scripts
- Enhance documentation
- Experiment with different configurations

## License

This project is for educational purposes. Please refer to individual component licenses for commercial use.

## Acknowledgments

Inspired by distributed systems and DevOps learning resources.