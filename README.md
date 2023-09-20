# Technical Documentation for the Medical Informatics Platform (MIP)  <!-- omit in toc --> 


A powerful federated data processing and analysis system that preserves patient privacy. More info on the [MIP Website](https://ebrains.eu/service/medical-informatics-platform/) 

# Table of Content <!-- omit in toc --> 

- [Preamble](#preamble)
- [8.0 Release](#80-release-major-updates)
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

# 8.0 Release Major Updates

**1)** Initial integration of differential privacy mechanisms within the Secure Multiparty Computation (SMPC) cluster, providing a global differential privacy guarantee for federated analytics, which gives a better utility for the same privacy budget compared to the local differential privacy alternative. The feature is provided as an opt-in deployment configuration option and allows fine-grained control over the enforcement of it (differential-privacy) in the SMPC pipeline.

**2)** The exareme2 engine was enhanced with workflow capabilities  and thus galaxy workflow engine were deprecated and removed.

**3)** A new algorithmic approach has been used, where each node is creating its own model and all the models are summed using the [federated averaging](https://www.educative.io/answers/what-is-federated-averaging-fedavg) technique.

**4)** New algorithms include naive bayes, cross validation included, for nominal and numerical CDEs and SVM (Support Vector Machine) which uses the federated averaging technique.

**5)** Documentation was added for integrating the ELK stack together with prometheus. These services, offer log aggregation, search and system resources monitoring across all nodes. 

**6)** Several additional improvements are included in the MIP 8.0 release, including aspects for its security, stability, operation and monitoring.

Current version, pertinent to this documentation is release 8.0 . See [the release notes and individual component releases that comprise MIP 8.0](./Components.md)

# MIP Components

The main [MIP building blocks](./Components.md) are listed along with the respective repositories that host them.

# Deployment

The MIP comes with a single code base but with two modes of deployment. One for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following location:

- [https://github.com/HBPMedical/mip-deployment](https://github.com/HBPMedical/mip-deployment)

# Federated Analysis Algorithms

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

- [Available federated analysis algorithms](./algorithms.md)
- [Exareme2 Analytic Engine](https://github.com/madgik/Exareme2)


# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [Data Management Guide](https://github.com/HBPMedical/mip-docs/blob/master/MIP_Data_management_documentation.md)

A detailed user guide for Data Quality Control tool can be found here:
 - [Data Quality Control Tool Guide](https://github.com/HBPMedical/DataQualityControlTool/wiki)

Data Catalogue is a component of the Medical Informatics Platform (MIP) for the Human Brain Project. Initially, it was designed and tasked to be the single source of truth of metadata descriptions for data residing in hospitals that have joined the MIP.
 - [Data Catalogue Guide](https://github.com/HBPMedical/DataCatalogue)

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

# Acknowledgement
This project/research received funding from the European Union’s Horizon 2020 Framework Programme for Research and Innovation under the Framework Partnership Agreement No. 650003 (HBP FPA).
