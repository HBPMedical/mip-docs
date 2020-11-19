# Preamble

This MIP System Description is an index for a collection of documents and other sources of information related to the Medical Informatics Platform. The intended audience comprises developers, technical deployment and support teams, and anyone else with a deep technical interest in the functioning of the MIP. Its purpose is to facilitate access to a range of information necessary to represent the current state of the MIP. It should provide adequate material for suitably qualified staff to understand how the MIP works, and to develop, deploy and operate the MIP.

This information is evolving along with the MIP so please make sure you consult the document version that is relevant to the indented, or preferably, latest version of the Medical Informatics Platform.

In the following sections, links and references to useful information is made available.

# High Level Description

For a high-level description of the MIP please consult the MIP Executive Summary at:

- [https://mip.ebrains.eu/documentation/Deployment%20Pack/1](https://mip.ebrains.eu/documentation/Deployment%20Pack/1)

The MIP site documentation section contains a lot of useful information you will want to go through at:

- [https://mip.ebrains.eu/documentation](https://mip.ebrains.eu/documentation)

For further reading, you can also have a look at some of the technical deliverables produced during the course of development. Some technical deliverables include:

- D8.5.2 (D52.2, D8 - SGA2 M12) Μedical Informatics Platform Releases - SOFTWARE & REPORT
- D8.5.3 (D52.3, D9 - SGA2 M20) Μedical Informatics Platform Releases  -  SOFTWARE & REPORT

These deliverables can be found at: [https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/](https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/)

# Release Notes

Current version to be released, pertinent to this documentation is release 6.3 . The release notes and individual component releases that comprise MIP 6.3 can be found at:

- [https://github.com/HBPMedical/mip-deployment/tree/6.3.0](https://github.com/HBPMedical/mip-deployment/tree/6.3.0)

# Architecture

For a high-level view of the architecture, the main building blocks and data flows, you can consult the available documentation at:

- <a href="./Architecture.md">Architecture</a>

# Installation Prerequisites

The installation prerequisites, hardware requirements and other considerations prior to deploying and running the MIP can be found at:

- [https://mip.ebrains.eu/documentation/Deployment%20Pack/3](https://mip.ebrains.eu/documentation/Deployment%20Pack/3)

# MIP Components

The main MIP building blocks are listed along with the respective repositories that host them at

- <a href="./Components.md">Components</a>

In these repositories you can find the source code, tests, documentation and other useful, technical, information.

A full list of the components, libraries, utilities and other artifacts can be found at:

- [https://github.com/HBPMedical/](https://github.com/HBPMedical/)

# Federated Analysis Algorithms

More information on the available federated analysis algorithms, although retrievable through the individual component list, can be directly found here:

- [https://github.com/madgik/exareme/tree/23.4.1/Exareme-Docker/src/mip-algorithms](https://github.com/madgik/exareme/tree/23.4.1/Exareme-Docker/src/mip-algorithms)

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [https://mip.ebrains.eu/documentation/User%20Manuals/6](https://mip.ebrains.eu/documentation/User%20Manuals/6)

# Deployment

The MIP comes with a single code base but with two modes of deployment. On for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following locations:

- Local: [https://github.com/HBPMedical/mip-deployment/tree/6.3.0](https://github.com/HBPMedical/mip-deployment/tree/6.3.0)
- Federation: [https://github.com/HBPMedical/mip-deployment/tree/6.3.0/Federation](https://github.com/HBPMedical/mip-deployment/tree/6.3.0/Federation)

In the case of federation, the analysis engine at this time requires a separate installation procedure that can be found at:

- [https://github.com/madgik/exareme/tree/23.4.1/Federated-Deployment](https://github.com/madgik/exareme/tree/23.4.1/Federated-Deployment)
