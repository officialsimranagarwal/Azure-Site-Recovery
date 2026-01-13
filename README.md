# Azure Site Recovery (ASR) Guide ☁️

![Azure](https://img.shields.io/badge/azure-%230072C6.svg?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Cloud](https://img.shields.io/badge/Cloud-Computing-blue?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Documentation-success?style=for-the-badge)

## 📖 Overview

This repository provides comprehensive documentation on **Azure Site Recovery (ASR)**, Microsoft's enterprise-grade Disaster Recovery as a Service (DRaaS) solution. It details the architecture and mechanisms for ensuring business continuity by orchestrating replication, failover, and recovery of workloads.

## 🏗️ Technical Architecture

The included documentation covers the following core ASR components:

### 1. Mobility Service
-   **Role**: Installed on each source machine (VMware VM or Physical Server).
-   **Function**: Captures data writes in memory and forwards them to the Process Server. Supports encryption in transit.

### 2. Process Server
-   **Role**: Handles replication data processing (caching, compression, encryption) before sending it to Azure.
-   **Placement**: Deployed within the on-premises environment.

### 3. Configuration Server
-   **Role**: Centralized management unit.
-   **Function**: Coordinates communication between on-premises infrastructure and Azure.

### 4. Recovery Services Vault
-   **Role**: The storage entity in Azure.
-   **Function**: Holds the replication data and recovery points.

## 🔄 Replication Workflow

The guide details the replication lifecycle:
1.  **Initial Replication**: A full copy of the source machine data is synchronized to the Azure storage account.
2.  **Delta Replication**: Continuous data changes (deltas) are tracked and synchronized to keep the recovery point objectives (RPO) low.
3.  **Consistency Points**:
    -   **Crash-Consistent**: Captures disk data only.
    -   **App-Consistent**: Captures disk data plus in-memory data (requires VSS).

## ⚠️ Failover & Failback

-   **Test Failover**: Creates a copy of the VM in an isolated Azure sandbox network to validate recovery plans without impacting production.
-   **Planned Failover**: Zero-data-loss failover for scheduled maintenance.
-   **Unplanned Failover**: Executed during actual disasters; attempts to sync pending data before cutting over.
-   **Failback**: The process of replicating data back from Azure to the on-premises site once the primary site is restored.

## 📂 Contents

-   **`Azure Site Recovery (1)_compressed.pdf`**: The master technical guide/presentation.

## 🚀 Getting Started

To access the technical documentation:
1.  Clone the repository:
    ```bash
    git clone https://github.com/officialsimranagarwal/Azure-Site-Recovery.git
    ```
2.  Review the PDF for detailed diagrams and configuration steps.

## 🤝 Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on how to propose changes to this documentation.

## 👤 Author

**Simran Agarwal**
-   [Profile](https://github.com/officialsimranagarwal)
-   [LinkedIn](https://linkedin.com/in/simran-agarwal-54751b191)

---
*Generated with ❤️ by Simran Agarwal*
