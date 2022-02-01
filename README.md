# Technical Documentation for the Medical Informatics Platform (MIP) 


A powerful federated data processing and analysis system that preserves patient privacy. More info on the [MIP Website](https://ebrains.eu/service/medical-informatics-platform/) 

# Preamble

This repository is an index for a collection of documents and other sources of information related to the Medical Informatics Platform. The intended audience comprises developers, technical deployment and support teams, and anyone else with a deep technical interest in the functioning of the MIP. Its purpose is to facilitate access to a range of information necessary to represent the current state of the MIP. It should provide adequate material for suitably qualified staff to understand how the MIP works, and to develop, deploy and operate the MIP.

This information is evolving along with the MIP so please make sure you consult the document version that is relevant to the indented, or preferably, latest version of the Medical Informatics Platform.

In the following sections, links and references to useful information is made available.

# 6.5 Release

The 6.5 release provides, besides general stability improvements, the capability to include additional variables in experiments. Variables can be calculated in an ad-hoc fashion through user-defined formula expressions, enhancements related to core descriptive statistics calculations will result in improved visualisation outputs for the user.

This new functionality can be used for Descriptive Statistics and Logistic Regression, and provides the ability to add transformations on continuous variables, with log, exp, centre, standardisation functions and a feature to add interactions between pairs of continuous variables.

Current version, pertinent to this documentation is release 6.5. See [the release notes and individual component releases that comprise MIP 6.5.](./Components.md)
 # MIP Components

The main [MIP building blocks](./Components.md) are listed along with the respective repositories that host them.
# Deployment

The MIP comes with a single code base but with two modes of deployment. On for local usage only, and one that enables the creation of a federation of nodes. Information on the different deployment approaches can be found in the following location:

- [https://github.com/HBPMedical/mip-deployment/tree/6.5.0](https://github.com/HBPMedical/mip-deployment/tree/6.5.0)

# Federated Analysis Algorithms

This includes documentation on existing algorithm federation approach as well as information related to creating a new algorithm.

- [Available federated analysis algorithms](./algorithms.md)
- [Exareme Analytic Engine](https://github.com/madgik/exareme/tree/24.3.0)


# Data Management

For all details relating to the Data Factory, how to manage your data and process it for use with the MIP, please consult the following document

- [Data Management Guide (PDF)](./docs/MIP_DATA_Management_Guideline_221221.pdf)

A detailed user guide for Data Quality Control tool can be found here:
 - [https://github.com/HBPMedical/DataQualityControlTool/wiki](https://github.com/HBPMedical/DataQualityControlTool/wiki)

Data Catalogue is a component of the Medical Informatics Platform (MIP) for the Human Brain Project. Initially, it was designed and tasked to be the single source of truth of metadata descriptions for data residing in hospitals that have joined the MIP.
 - [https://github.com/HBPMedical/DataCatalogue](https://github.com/HBPMedical/DataCatalogue)

# High Level Description

For a high-level description of the MIP please consult:

- [Executive Summary](./deployment-pack/executive-summary.md)
- [The MIP: A powerful federated data processing and analysis system that preserves patient privacy](https://ebrains.eu/service/medical-informatics-platform/) on EBRAINS research infrastructure

For further reading, you can also have a look at some of the technical deliverables produced during the course of development. Some technical deliverables include:

- [D8.5.2 (D52.2, D8 - SGA2 M12) Μedical Informatics Platform Releases - SOFTWARE & REPORT (PDF)](https://sos-ch-dk-2.exo.io/public-website-production/filer_public/e0/1d/e01dd6b7-7223-4ecd-b7fb-468eab47a62e/d852_d522_d8_sga2_m12_accepted_190722.pdf)
- [D8.5.3 (D52.3, D9 - SGA2 M20) Μedical Informatics Platform Releases  -  SOFTWARE & REPORT (PDF)](https://sos-ch-dk-2.exo.io/public-website-production/filer_public/a6/97/a697ebed-cc74-463d-a4d5-c75e2b922c2b/d853_d523_d9_sga2_m20_accepted_200731.pdf)

These deliverables can be found at: [https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/](https://www.humanbrainproject.eu/en/about/governance/deliverables/sga2-phase/)

# Architecture

[High-level view of the architecture](./Architecture.md), the main building blocks and data flows.

# Installation Prerequisites

- See [Deployment Pack](deployment-pack/README.md)

# Tutorials
- Basic skills to start working with the MIP and conduct initial experiments [Videos List](./video-tutorial.md)
- [MIP Guide](./docs/mip_guide_updated.pdf)

A full list of the components, libraries, utilities and other artifacts can be found at:

- [https://github.com/HBPMedical/](https://github.com/HBPMedical/)
