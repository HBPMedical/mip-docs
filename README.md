# Technical Documentation for the Medical Informatics Platform (MIP)  <!-- omit in toc --> 


A powerful federated data processing and analysis system that preserves patient privacy. More info on the [MIP Website](https://ebrains.eu/data-tools-services/medical-analytics/medical-informatics-platform) 

# Table of Content <!-- omit in toc --> 

- [Preamble](#preamble)
- [8.5 Release](#85-release-major-updates)
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

# MIP 8.5 Release – Major Updates

## **Exareme2 – Federated Strategy Framework Integration**

Exareme2 has been enhanced with a new *exaflow* pipeline and an updated core engine. The system now supports integration with frameworks such as Flower, that can be used to plug in federated learning strategies. As part of this evolution, the aggregation approach has been redesigned to operate through a dedicated aggregation component within the pipeline.

## **Frontend Enhancements**

The MIP frontend has been improved with updated visuals, refined aesthetics, and additional features that enhance data visualization and user interaction.

## **Migration to Managed Cluster Setup**

The MIP infrastructure has been migrated to a fully managed cluster setup, leveraging:

* ArgoCD, Submariner, and other cloud-native tooling for GitOps-driven, scalable deployments
* Infrastructure-as-code workflows, maintained in the following repository:
  [https://github.com/Medical-Informatics-Platform/mip-infra](https://github.com/Medical-Informatics-Platform/mip-infra)

## **Data Catalog Revamp**

The Data Catalog has been completely rebuilt to:

* Represent all existing MIP federations
* Describe each pathology’s data model, including variables, attributes, and hierarchical relationships
* Provide an interactive tree visualization using D3 TidyTree

The new Data Catalog is available here:
[https://datacatalogue.mip.ebrains.eu](https://datacatalogue.mip.ebrains.eu)

## **ECK-based Monitoring**

A unified monitoring layer using Elastic Cloud on Kubernetes (ECK) has been deployed across the managed cluster, enabling improved observability and operational insight for all federations.

# MIP Components

The main [MIP building blocks](./Components.md) are listed along with the respective repositories that host them.

# Deployment

The MIP comes with a single code base but with two modes of deployment. One for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following location:

- [https://github.com/HBPMedical/mip-deployment/tree/8.5.0](https://github.com/HBPMedical/mip-deployment/tree/8.5.0)

# Federated Analysis Algorithms

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

- [Available federated analysis algorithms](./algorithms.md)
- [Exareme2 Analytic Engine](https://github.com/madgik/Exareme2/tree/0.28.0)


# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [Data Management Guide](https://github.com/HBPMedical/mip-docs/blob/master/MIP_Data_management_documentation.md)

A detailed user guide for Data Quality Control tool can be found here:
 - [Data Quality Control Tool Guide](https://github.com/HBPMedical/DataQualityControlTool/wiki)

Data Catalog is a component of the Medical Informatics Platform (MIP) for the EBrains. It enables seamless management, visualization, and access to data models and medical conditions.
 - [Data Catalog Guide](https://github.com/madgik/datacatalog/tree/1.0.0)

# High Level Description

For a high-level description of the MIP please consult:

- [The MIP: A powerful federated data processing and analysis system that preserves patient privacy](https://ebrains.eu/data-tools-services/medical-analytics/medical-informatics-platform) on EBRAINS research infrastructure


# Architecture

[High-level view of the architecture](./Architecture.md), the main building blocks and data flows.

# Installation Prerequisites

- See [Deployment Pack](deployment-pack/README.md)

# Tutorials
- Basic skills to start working with the MIP and conduct initial experiments [Videos List](./video-tutorial.md)

# Acknowledgement
This project/research received funding from the European Union’s Horizon 2020 Framework Programme for Research and Innovation under the Framework Partnership Agreement No. 650003 (HBP FPA).
