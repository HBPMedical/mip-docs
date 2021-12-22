# Preamble

This repsoitory is an index for a collection of documents and other sources of information related to the Medical Informatics Platform. The intended audience comprises developers, technical deployment and support teams, and anyone else with a deep technical interest in the functioning of the MIP. Its purpose is to facilitate access to a range of information necessary to represent the current state of the MIP. It should provide adequate material for suitably qualified staff to understand how the MIP works, and to develop, deploy and operate the MIP.

This information is evolving along with the MIP so please make sure you consult the document version that is relevant to the indented, or preferably, latest version of the Medical Informatics Platform.

In the following sections, links and references to useful information is made available.

# High Level Description

For a high-level description of the MIP please consult:

- [Executive Summary](./deployment-pack/executive-summary.md)
- [The MIP: A powerful federated data processing and analysis system that preserves patient privacy](https://ebrains.eu/service/medical-informatics-platform/) on EBRAINS research infrastructure

For further reading, you can also have a look at some of the technical deliverables produced during the course of development. Some technical deliverables include:

- [D8.5.2 (D52.2, D8 - SGA2 M12) Μedical Informatics Platform Releases - SOFTWARE & REPORT (PDF)](https://sos-ch-dk-2.exo.io/public-website-production/filer_public/e0/1d/e01dd6b7-7223-4ecd-b7fb-468eab47a62e/d852_d522_d8_sga2_m12_accepted_190722.pdf)
- [D8.5.3 (D52.3, D9 - SGA2 M20) Μedical Informatics Platform Releases  -  SOFTWARE & REPORT (PDF)](https://sos-ch-dk-2.exo.io/public-website-production/filer_public/a6/97/a697ebed-cc74-463d-a4d5-c75e2b922c2b/d853_d523_d9_sga2_m20_accepted_200731.pdf)

These deliverables can be found at: [https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/](https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/)

# Release Notes

Current version, pertinent to this documentation is release 6.4. The release notes and individual component releases that comprise MIP 6.4 can be found at:

- [https://github.com/HBPMedical/mip-deployment/tree/6.4.0](https://github.com/HBPMedical/mip-deployment/tree/6.4.0)
- [Frontend Changelog](https://github.com/HBPMedical/portal-frontend/blob/main/CHANGELOG.md)

# Architecture

For a high-level view of the architecture, the main building blocks and data flows, you can consult the available documentation at:

- <a href="./Architecture.md">Architecture</a>

# Installation Prerequisites

The installation prerequisites, hardware requirements and other considerations prior to deploying and running the MIP can be found at:

- [Deployment Pack (PDF)](./docs/MIP_Executive_Summary_V02.00_7960b8432e.pdf)
- [Installation and License Agreement (PDF)](./docs/MIP_Installation_and_License_Agreement_-_V02.10_210c5d6538.pdf)
- [Installation Prerequisites and Installation Guide](./deployment-pack/install-prerequisites.md)
- [Ethics and Legal Requirements](./deployment-pack/ethics-legal.md)
- [FAQ](./deployment-pack/faq.md)


- [Data Sharing and Processing Agreement](./docs/Data_Sharing_and_Processing_Agreement_June2021_v2.pdf)
- [Data Transfer Agreement](./docs/DTA_EBRAINS_June2021_v2.pdf)
- [MIP Service Agreement and Software Licences](./docs/MIP_Service_Agreement_and_Software_Licenses_Dec21.pdf)

# MIP Components

The main MIP building blocks are listed along with the respective repositories that host them at

- <a href="./Components.md">Components</a>

In these repositories you can find the source code, tests, documentation and other useful, technical, information.

A full list of the components, libraries, utilities and other artifacts can be found at:

- [https://github.com/HBPMedical/](https://github.com/HBPMedical/)

# Federated Analysis Algorithms

- [Available federated analysis algorithms](./algorithms.md)

Retrievable through the individual component list, can be directly found here:

- [https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms](https://github.com/madgik/exareme/tree/master/Exareme-Docker/src/mip-algorithms)

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [Data Management Guide (PDF)](./docs/MIP_DATA_Management_Guideline_221221.pdf)

A detailed user guide for Data Quality Control tool can be found here:
 - [https://github.com/HBPMedical/DataQualityControlTool/wiki](https://github.com/HBPMedical/DataQualityControlTool/wiki)

Data Catalogue is a component of the Medical Informatics Platform (MIP) for the Human Brain Project. Initially, it was designed and tasked to be the single source of truth of metadata descriptions for data residing in hospitals that have joined the MIP.
 - [https://github.com/HBPMedical/DataCatalogue](https://github.com/HBPMedical/DataCatalogue)

# Deployment

The MIP comes with a single code base but with two modes of deployment. On for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following locations:

- Local: [https://github.com/HBPMedical/mip-deployment](https://github.com/HBPMedical/mip-deployment)
- Federation: [https://github.com/HBPMedical/mip-deployment/tree/6.4.0/Federation](https://github.com/HBPMedical/mip-deployment/tree/6.4.0/Federation)

In the case of federation, the analysis engine at this time requires a separate installation procedure that can be found at:

- [https://github.com/madgik/exareme/tree/24.1.2/Federated-Deployment](https://github.com/madgik/exareme/tree/24.1.2/Federated-Deployment)

# Tutorials
- Basic skills to start working with the MIP and conduct initial experiments [Videos List](./video-tutorial.md)
- [MIP Guide](./docs/mip_guide_updated.pdf)
