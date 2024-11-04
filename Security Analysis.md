# Medical Informatics Platform Security Analysis

This document provides a comprehensive security analysis of the MIP federated learning platform, covering
infrastructure, node access, communication protocols, user access controls, and auditing mechanisms.

## Table of Contents
1. [Overall Architecture](#overall-architecture)
2. [Infrastructure](#infrastructure)
3. [Node Access Security](#node-access-security)
4. [Inter-node Communication](#inter-node-communication)
5. [Kubernetes Cluster](#kubernetes-cluster)
6. [Federated Learning Analysis Engine](#federated-learning-analysis-engine)
7. [Webapp User Access](#webapp-user-access)
8. [Auditing and Logging](#auditing-and-logging)

---

## Overall Architecture

![Overall Architecture](/images/architecture.png)

---

## Infrastructure

The MIP platform is deployed on virtual machines hosted by CSCS as well as on VMs provided by remote
partners, such as hospitals.

- **Node-Level Security**: CSCS ensures security, storage isolation, and infrastructure protection.
For more information you can check the [CSCS website](https://www.cscs.ch/computers/alps).
- **VM Maintenance**: The MIP team keeps VMs updated with the latest patches and secures them at the
  application level, implementing measures to prevent unauthorized access and safeguard application
  integrity.

---

## Node Access Security

- **CSCS Cluster Nodes**: Access is managed via SSH keys with regular rotation. Only authorized DevOps
  team members are allowed access to install the VPN layer and join the Kubernetes federation cluster.
- **Remote Partner-Owned VMs**: Access security is managed by the partner organization, typically
  involving SSH key-based access with IP restrictions to ensure secure, limited access.

---

## Inter-node Communication

Secure connectivity between cluster nodes, including both CSCS and remote partner nodes, is established
using a SoftEther VPN server configured with the OpenVPN protocol. This VPN enforces SSL-encrypted
communication, preventing unauthorized external access.

- **Bastion Host**: All access to nodes is routed through a bastion host (jumper node), limiting direct
  access and reducing the network’s attack surface.
- **Kubernetes Integration**: Once connected through the VPN, nodes securely join a Kubernetes cluster,
  allowing seamless and secure inter-node communication.

---

## Kubernetes Cluster

Access to the Kubernetes cluster is restricted to a dedicated Kubernetes admin VM, which is exclusively
used for deploying and monitoring Kubernetes services.

- **Access Control**: Access to the kubeadmin VM requires SSH key authentication and connection via the
  bastion (jumper) node.
- **RBAC**: Role-Based Access Control is not implemented due to the small size of the DevOps team.

### Network Policies (Work in Progress)

Network policies are under development to restrict communication between nodes to only necessary
connections, reducing unnecessary network exposure and enhancing security.

---

## Federated Learning Analysis Engine

![Security Architecture](/images/architecture-security.jpg)

### Communication

Exareme2, the federated learning engine, is deployed as Kubernetes pods, relying on the secure VPN for
inter-node communication.

- **Node-to-Node Communication**:
    1. **Central-to-Local Node**: The central node instructs each local node to initiate computations and
       return results.
    2. **Local-to-Central Node**: Local nodes send computation results back to the central node.

- **Message Queue**: RabbitMQ is used for communication from the central node to local nodes, enabling
  structured task dispatch.
- **SMPC**: Results are returned via the Secure Multi-Party Computation (SMPC) protocol, maintaining
  stringent privacy guarantees.

### Local Exareme2 Service Security

The Exareme2 service on each local node is secure by design, restricting the actions that even the
central node can execute on protected data. Data leaving the local node is limited to aggregated results,
with minimum data thresholds enforced to prevent privacy breaches, ensuring robust security for partner data.

---

## Webapp User Access

User access to the web application is managed through Keycloak, serving as the identity provider. Access
can be provisioned either through the eBrains service for external users or as a cluster-specific service
for internal users.

- **Backend Security**: The backend leverages the OAuth2 protocol with OpenID Connect (OIDC) for secure,
  standards-compliant authentication.
- **CSRF Protection**: Additional protections are implemented to defend against Cross-Site Request Forgery
  (CSRF) attacks.

### Authentication

For eBrains users, authentication is granted upon request based on the user’s role, specific use case,
and relevance to the MIP platform. This ensures that only authorized users with approved purposes can
log into the system.

### Authorization

Authorization is highly customizable and can be configured at multiple levels:
- **Data Models**: Access can be granted to entire data models.
- **Specific Datasets**: Permissions can be limited to relevant datasets.
- **Data Manager Permissions**: Users can manage data within their authorized scope.
- **Data Model Administrator**: Administrators have full access to all data and experiments.

This fine-grained authorization allows precise control over access to resources, aligning permissions
with user responsibilities and data privacy requirements.

---

## Auditing and Logging

Comprehensive logging across all services is implemented and aggregated using the ELK stack
(Elasticsearch, Logstash, and Kibana).

- **Logged Activities**:
    1. **User Experiment Execution**: Records user-initiated experiments, providing insights into usage
       patterns.
    2. **Dataset Access**: Tracks access to datasets, supporting data security and compliance.
    3. **System Errors**: Logs system errors to aid in prompt issue resolution.
    4. **User Erroneous Requests**: Captures incorrect or malformed requests to improve user experience.

These logs are monitored through the ELK stack to ensure system operation and timely issue detection.

### Trace IDs

Trace IDs are used across logs, linking entries related to specific user actions. This enables efficient
monitoring and troubleshooting, improving system insights and enabling faster error recovery.

### VPN and VM Access Logging

VPN and VM access events are logged both at the bastion host (jumper node) and within individual VMs,
providing a detailed record of access attempts across the infrastructure. This logging ensures continuous
monitoring of critical access points for security and compliance.

---
