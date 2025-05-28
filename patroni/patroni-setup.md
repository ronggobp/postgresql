# PostgreSQL High Availability Cluster using Patroni, ETCD, and HAProxy

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Server Information](#server-information)
- [Software Information](#software-information)
- [Steps Summary](#steps-summary)
- [Installation Steps](#installation-steps)
  - [1. Install PostgreSQL](#1-install-postgresql)
  - [2. Install and Configure ETCD](#2-install-and-configure-etcd)
  - [3. Install Patroni](#3-install-patroni)
  - [4. Configure Patroni YAML](#4-configure-patroni-yaml)
  - [5. Install and Configure HAProxy](#5-install-and-configure-haproxy)
  - [6. Install and Configure PgBouncer](#5-install-and-configure-pgbouncer)
  - [7. Install and Configure Keepalived (VIP)](#6-install-and-configure-keepalived-vip)
- [Service Information](#service-information)
- [Monitoring and Testing](#monitoring-and-testing)
- [Conclusion](#conclusion)

## Overview

This guide explains how to build a **Highly Available PostgreSQL Cluster** using **Patroni**, **ETCD**, and **HAProxy**. The goal is to achieve automatic failover, replication, and seamless client redirection in the event of node failures.

## Architecture

## Server Information
| Hostname    | IP Address   | Role                               |
| ----------  | ------------ | ---------------------------------- |
| `patroni1`  | 192.168.1.6  | PostgreSQL + Patroni + ETCD        |
| `patroni2`  | 192.168.1.7  | PostgreSQL + Patroni + ETCD        |
| `patroni3`  | 192.168.1.8  | PostgreSQL + Patroni + ETCD        |
| `pbhap1`    | 192.168.1.9  | HAProxy + PgBouncer + Keepalived   |
| `pbhap2`    | 192.168.1.10 | HAProxy + PgBouncer + Keepalived   |
| `vip`       | 192.168.1.11 | Virtual IP - Managed by Keepalived |


