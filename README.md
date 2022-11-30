# Technical Documentation for the Medical Informatics Platform (MIP)  <!-- omit in toc --> 


A powerful federated data processing and analysis system that preserves patient privacy. More info on the [MIP Website](https://ebrains.eu/service/medical-informatics-platform/) 

# Table of Content <!-- omit in toc --> 

- [Preamble](#preamble)
- [7.0 Release](#50-release)
- [MIP Components](#mip-components)
- [Deployment](#deployment)
- [Federated Analysis Algorithms](#federated-analysis-algorithms)
- [Data Management](#data-management)
- [High Level Description](#high-level-description)
- [Architecture](#architecture)
- [Installation Prerequisites](#installation-prerequisites)
- [Tutorials](#tutorials)

# Preamble

This repository is an index for a collection of documents and other sources of information related to the Medical Informatics Platform. The intended audience comprises developers, technical deployment and support teams, and anyone else with a deep technical interest in the functioning of the MIP. Its purpose is to facilitate access to a range of information necessary to represent the current state of the MIP. It should provide adequate material for suitably qualified staff to understand how the MIP works, and to develop, deploy and operate the MIP.

This information is evolving along with the MIP so please make sure you consult the document version that is relevant to the indented, or preferably, latest version of the Medical Informatics Platform.

In the following sections, links and references to useful information is made available.

# 7.0 Release

The 7.0 release integrates a mechanism for Secure Multiparty Computation (SMPC), providing cryptographic guaranties that local, partial, results are never known. The feature is provided as an opt-in deployment configuration option and allows fine grained control over the enforcement of the SMPC pipeline.

Additionally, MIP deployment and operations has been moved to an orchestrator based approach and is currently offered through a Kubernetes managed cluster.

Several improvements are included in the MIP 7.0 release, including aspects for its scalability, performance, stability, operation and management. Health monitoring endpoints and visualization improvements have been introduced while experiment outcomes are now comprehensively bundled and are available for exporting from the end-users

Current version, pertinent to this documentation is release 7.0. See [the release notes and individual component releases that comprise MIP 7.0.0.](./Components.md)

# MIP Components

The main [MIP building blocks](./Components.md) are listed along with the respective repositories that host them.

# Deployment

The MIP comes with a single code base but with two modes of deployment. On for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following location:

- [https://github.com/HBPMedical/mip-deployment/tree/7.0.0](https://github.com/HBPMedical/mip-deployment/tree/7.0.0)

# Federated Analysis Algorithms

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

- [Available federated analysis algorithms](./algorithms.md)
- [Exareme Analytic Engine](https://github.com/madgik/exareme/tree/24.5.0)
- [MIP-Engine Analytic Engine](https://github.com/madgik/MIP-Engine/tree/0.13.2)


# SMPC Integration

Integration with the SMPC engine is provided. The mechanism of Secure Multiparty Computation (SMPC) provides cryptographic guaranties that local, partial, results are never known. This way, a distributed system can behave like a single, centralized database. On top of this privacy enhancing technique, the MIP continues offering its federated analysis with its existing privacy aware methodologies, orthogonal to the additional layer of cryptographic privacy.

The SMPC enabling layer is offered as an opt-in feature at the time of federation setup, allowing the provisioning and bootstrapping of an SMPC cluster. In addition to the cluster bootstrapping and configuration options given at infrastructure setup time, furhter, refined control can be provided at a per algorithm selection level to permit or enforce the usage of the SMPC pipelining.

# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [Data Management Guide (PDF)](./docs/MIP_DATA_Management_Guideline_221221.pdf)

A detailed user guide for Data Quality Control tool can be found here:
 - [https://github.com/HBPMedical/DataQualityControlTool/wiki](https://github.com/HBPMedical/DataQualityControlTool/wiki)

Data Catalogue is a component of the Medical Informatics Platform (MIP) for the Human Brain Project. Initially, it was designed and tasked to be the single source of truth of metadata descriptions for data residing in hospitals that have joined the MIP.
 - [https://github.com/HBPMedical/DataCatalogue](https://github.com/HBPMedical/DataCatalogue)

# High Level Description

For a high-level description of the MIP please consult:

- [The MIP: A powerful federated data processing and analysis system that preserves patient privacy](https://ebrains.eu/service/medical-informatics-platform/) on EBRAINS research infrastructure


# Architecture

[High-level view of the architecture](./Architecture.md), the main building blocks and data flows.

# Installation Prerequisites

- See [Deployment Pack](deployment-pack/README.md)

# Tutorials
- Basic skills to start working with the MIP and conduct initial experiments [Videos List](./video-tutorial.md)
- [MIP Guide](./docs/mip_guide_updated.pdf)

