# Testing and Validation

## Overview

This document describes the validation performed after deploying the Amazon RDS MySQL database.

The tests verify database availability, network configuration, endpoint information, and connectivity from the EC2 environment.

---

## 1. RDS Database Availability

### Objective

Verify that the Amazon RDS database was successfully created and reached an available state.

### Validation

The RDS console was used to verify the database status after deployment.

### Evidence

_Add screenshot here._

---

## 2. Security Group Configuration

### Objective

Verify that the Security Group was configured to allow the required database traffic.

### Validation

The Security Group configuration was reviewed to verify the network rule associated with the MySQL database connection.

The required MySQL port is:

```text
3306/TCP
