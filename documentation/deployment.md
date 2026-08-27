# RDS MySQL Database Deployment

## Overview

This document describes the deployment and configuration of an Amazon RDS MySQL database and the network configuration required to establish connectivity from an EC2 environment.

The deployment covers database configuration, storage, connectivity, Security Group configuration, endpoint identification, and database connection validation.

---

## 1. Database Engine Selection

The RDS database was configured using the MySQL database engine.

The required database engine and version were selected during the RDS database creation process.

### Configuration

- Database service: Amazon RDS
- Database engine: MySQL
- Database deployment: RDS database instance

---

## 2. Database Instance Configuration

The RDS database configuration included:

- Number of RDS instances
- Database identifier
- Administrator username
- Administrator password
- Instance hardware configuration

Database credentials were configured during deployment and are not included in this repository.

---

## 3. Storage Configuration

The database storage configuration was reviewed during deployment.

RDS storage settings were configured according to the requirements of the practice.

The deployment also includes the option for automatic storage scaling.

---

## 4. Network Connectivity

The RDS database requires network connectivity to allow clients to establish a database connection.

The practice demonstrates two possible approaches:

1. Connect the database directly to an EC2 compute resource using the AWS connectivity configuration.
2. Configure the network connectivity manually using Security Groups.

For this deployment, connectivity was configured manually to demonstrate the underlying network access requirements.

---

## 5. Security Group Configuration

A Security Group was created to control network access to the RDS database.

The Security Group defines the network rules required for database connectivity.

The database connection uses the MySQL TCP port:


3306S

---

## 6. Database Creation

After configuring the database, storage, connectivity, and Security Group settings, the RDS database was created.

The deployment process generated an RDS database endpoint that can be used by database clients to establish a connection.

---

## 7. RDS Endpoint

After the database became available, the RDS endpoint and database port were identified.

The endpoint provides the hostname required by clients to connect to the database.

Example:
database-1.xxxxxxxxxxxx.us-east-1.rds.amazonaws.com

MySQL uses TCP port:3306

The actual endpoint used during the practice is intentionally not hardcoded into the documentation because RDS endpoints are resource-specific.

---

## 8. Database Connectivity from EC2

The database connection was tested from an EC2 environment using the MySQL client.

The general connection format used during the practice was:
mysql -h <RDS_ENDPOINT> -P 3306 -u admin -p'<DB_PASSWORD>'

The database password is intentionally represented as a placeholder and is not stored in this repository.

The practice also demonstrates the use of SSL parameters for the database connection.

---

## 9. Connection Validation

The RDS database connection was tested after the database became available.

The connection test verified that:

The RDS endpoint was reachable.
The MySQL port was correctly configured.
The Security Group allowed the required network traffic.
The database credentials were accepted.
The MySQL client successfully connected to the RDS database.

---

## 10. Deployment Result

The Amazon RDS MySQL database was successfully deployed and configured.

Connectivity from the EC2 environment was validated using the database endpoint and MySQL port 3306.

The deployment demonstrates the basic integration of:

EC2
  |
  | TCP 3306
  |
Security Group
  |
  |
Amazon RDS
  |
  |
MySQL

---

## Security Considerations

The following information is intentionally excluded from this repository:

Database passwords
AWS access keys
Secret keys
Other sensitive credentials

Database access should be restricted through Security Groups and only the required ports should be exposed.
