
# **The Medical Informatics Platform (MIP)**

# **Data Management Guideline**

**Author (MIP Support Team)**

**Version 4.0**

**2023 ****02 15******

# Acronyms

| HBP | Human Brain Project |
|:--- |:--- |
| MIP | Medical Informatics Platform |
| CHUV | Centre Hospitalier Universitaire Vaudois |
| AUEB | Athens University of Economics and Business |
| EHR | Electronic Health Record |
| SQL | Structured Query Language |
| CDEs | Common Data Elements |
| JSON | JavaScript Object Notation; is open-standard file format or data interchange format |
| CSV | Comma-separated values file; is a delimited text file that uses a comma to separate values. |
| MRI | Magnetic Resonance Imaging |
| DICOM | Digital Imaging and Communications in Medicine |
| NIFTI | Neuroimaging Informatics Technology Initiative |
| DQC-Tool | Data Quality Control Tools |
| GUI | Graphical User Interface |
| DC | Data Catalogue |

# **Table of Contents**

* [Acronyms](#acronyms)

* [About this Document](#about-this-document)

  * [Target Audience](#target-audience)

  * [Document Overview](#document-overview)

* [Concepts and Definitions](#concepts-and-definitions)

* [The MIP](#the-mip)

* [Data Management and Processing](#data-management-and-processing)

  * [Extraction and compilation of clinical data as a csv file](#extraction-and-compilation-of-clinical-data-as-a-csv-file)

  * [Definition of Common Data Elements for a medical condition](#definition-of-common-data-elements-for-a-medical-condition)

  * [Data cleaning, validation, and upload](#data-cleaning-validation-and-upload)

# About this Document

## Target Audience

This document is targeting data processors and members of data controllers from institutes interested in analysing their clinical and research data within the MIP. It mainly addresses technical coordinators and data managers who want to prepare their data to be ingested into the MIP analysis engine.

The document provides the information needed to understand:

- The approach of data processing to achieve data ingestion to the MIP.
- The tools that have been developed to facilitate the data processing (The MIP Data Catalogue, the MRI parallel neuromorphometrics pipeline, and the MIP Data Quality Control Tool (MIP-DQC Tool).
- Link to the user guide for each of these tools

## Document Overview

This document describes the MIP Data architecture, and for which purpose it was assembled. It explains the overall data processing required to conform to MIP standards before being uploaded to the MIP and how the MIP Data Quality tools shall be used to help achieving these standards.

It is a step-by-step guide covering data end to end processing and it provides links to additional documentation and detailed instructions described in the different GitHub repositories and shall not be seen in isolation.

# Concepts and Definitions

**Common Data Elements (CDEs)**

A set of standard variables defined by clinical experts and data scientists, which would be used by researchers to perform analysis on specific medical conditions at the federation level. In the MIP context, we use the term CDEs to refer to the standardized federated data models only.

**Data Element**

In metadata, the term data element is an atomic unit of data that has precise meaning or precise semantics. [Beynon-Davies P. (2004). Database Systems 3rd Edition. Palgrave, Basingstoke, UK]

**Data Models (Metadata)**

Data Model (Metadata) describes the structure of database variables found in specific extract of a hospital's database, including descriptive metadata, structural metadata, administrative metadata, reference metadata and statistical metadata. [1] Zeng, Marcia (2004). "Metadata Types and Functions". NISO. Archived from the original on 7 October 2016. Retrieved 5 October 2016.

**Database Variables:**

A variable or scalar is a storage address (identified by an index or address) paired with an associated symbolic name, which contains some known or unknown quantity of information referred to as a value. [Knuth, Donald (1997). The Art of Computer Programming. 1 (3rd ed.). Reading, Massachusetts: Addison-Wesley. p. 3-4.]

**EBRAINS**

EBRAINS is a new digital research infrastructure, created by the EU-funded Human Brain Project, that gathers an extensive range of data and tools for brain-related research. EBRAINS will capitalize on the work performed by the Human Brain Project teams in digital neuroscience, brain medicine, and brain-inspired technology and will take it to the next level.

**Electronic Health Records (EHR)**

Health information and clinical records registered per each patient per visit in the hospital's database (Oracle, SQL or any database systems) and usually transferred in db or CSV format. EHR usually contain different levels of data; we might define them in this context as spaces, domain, and sub-domain. For example, General space might include demographic, social status or patient's medical history as different data domains. On the other hand, EHR contain other data spaces related to the specific medical condition such as Dementia or Epilepsy where each space includes specific domain and sub-domain, such as medical assessments and tests, diagnoses, treatment, and operations, etc.

**Medical Conditions**

Diseases are often known to be medical conditions that are associated with specific symptoms and signs. ["Disease" at Dorland's Medical Dictionary]

# The MIP

The [Medical Informatics Platform](https://mip.ebrains.eu/) (MIP) for the [Human Brain Project](https://www.humanbrainproject.eu/) is an innovative platform that provides an interface for various investigators (_i.e._ clinicians, neuroscientists, epidemiologists, researchers, health managers) to access, explore and analyse anonymised medical data that are locked and hosted in their original hospital or research centre. Data exploration and analysis can then be performed without moving the data from the hospital where data reside, and hence without infringing on patient privacy.

The MIP has been designed adopting a 2-tier architecture, which guarantees hospital data protection and privacy by design. The MIP offers two main solutions (see diagram below):

- The MIP-Local Node contains data that can only be accessed and analysed by the Local Data Manager and its accredited staff from the hospital.
- The MIP-Federated Node contains anonymized data and can be connected to other MIP-Federated Nodes located in other hospitals when the decision is made to join the MIP Network (medical condition-based federations of hospitals) and to provide access to hospital data to members of the network.

Upon signed agreements (between the data provider`s institution and the CHUV), and admission to the MIP Network, accredited researchers can query multiple MIP federated Nodes and obtain aggregated results. Queries of the MIP-Federated Nodes does not allow to copy, download, or upload any data, nor to see individual patient's data.

![data governance](https://github.com/HBPMedical/mip-docs/blob/master/images/The%20MIP%20Data%20Governance%20flow.jpg)

# Data Management and Processing

Data originating from diverse hospitals are highly heterogeneous in nature and hence cannot be uploaded into the MIP _per se_. Multiple steps need to be done that are represented in the following figure and which can be regrouped in two main groups:

- Identification of variables that will be made available in the MIP to fulfil the scientific analysis objective and definition of the Data Model (Metadata). In case of a federated MIP, all hospitals must agree to a Common Data Elements (CDEs).
- Data pre-processing to conform to the CDEs predefined and to the MIP's standard formats.

The standard format of the dataset file is .csv UTF-8. Because csv format doesn't allow to keep the Metadata structure, a second file is required, which corresponds to the CDEs for which the MIP standard format is JSON.

To help data managers to go through these processes, three main tools have been developed until now:

- **The MIP Data Catalogue** : Web-based application that is used to explore and manage MIP Data Models and CDEs pre-defined by the federation's community or the use case group. All the existing Medical Conditions, Federations and Hospitals and their associated Common Data Elements (CDEs) are available within the MIP Data Catalogue, which is the unique source of reference for the MIP and the MIP-DQC Tool. The MIP Data Catalogue can be accessed at the following address ([HERE](https://datacatalogue.hbpmip.link/)). _It is recommended to use any browser except Firefox._
- **The MRI parallel neuromorphometrics pipeline:** A python wrapper to run the Statistical Parametric Mapping SPM12 pipeline in parallel with Matlab over multiple CPU cores.
- **The MIP Data Quality Control Tool (MIP-DQC Tool)**: A standalone software that provides hospital personnel an easy way to explore, transform and validate their dataset based on the CDEs before uploading them into the MIP. MIP-DQC Tool has both, a Command Line Interface (CLI) and a Graphical User Interface (GUI), with only the latter having the full set of functionalities. The MIP-DQC Tool GUI version has the following functionalities:
  - Inference of a dataset's schema and producing a schema file in Frictionless json or the MIP Data Catalogue's excel format.
  - Validating the MIP Data Models or CDEs pre-defined by the federation's community or the use case group.
  - Translating the MIP Data Models or CDEs from xlsx format to json format.
  - Validating the hospital tabular (csv) data against the MIP Data Models or CDEs and producing a validation report and some overall statistics about the data.
  - Data cleaning capability based on the previously performed validation report.
  - Designing and performing schema mapping of an incoming hospital dataset to a certain Pathology's Common Data Element (CDE) schema.
  - Producing a DICOM MRI validation and statistical report, based on the meta-data headers.
  - The tabular (csv) data validation functionality has the option of downloading the pathology`s CDE metadata directly from the MIP Data Catalogue's API. Please note that this option is not available in the CLI version.
  - The schema mapping functionality is performed by the MIPMap engine packaged in a Docker container, which runs in the background. Please note that this option is not available in the CLI version.

The user guide for each of these three tools can be found in the respective GitHub repositories. 
  - [The MIP Data Catalogue](https://datacatalogue.hbpmip.link/)
  - [The MIP Data Quality Control Tool](https://github.com/HBPMedical/DataQualityControlTool/wiki)
  - [The MRI parallel neuromorphometrics pipeline](https://github.com/HBPMedical/mri-parallel-nmm-pipeline)

Through description of the steps required before being able to upload data on the MIP, the information of which tool can be used is provided in italics. The following table lists the sequential steps as well as the tool that can be used to simplify this process.

***Table 1*: MIP Data extraction and compilation and available Tools**
|| **1srt step** | **2nd step (optional)** | **3rd step (optional)** |
| --- | --- | --- | --- |
| **Tasks** | Extract the clinical data as a csv file | Extract the brain volumes from the nifti to the csv file | Merge the brain volumes with the clinical data |
| **Tools** | | MRI parallel neuromorphometrics pipeline | |
 
***Table 2*: MIP Common Data Element definition and available Tools**
|| **1srt step** | **2nd step** | **3rd step (optional)** | **4th step** |
| --- | --- | --- | --- | --- |
| **Tasks** |Infer the data schema from the csv file to produce the Data Model xlsx file | For the federation, there should be a discussion around the standardization of variables in the Data Model to produce a standard Common Data Element (CDE, or Data Model) as an xlsx file | The MIP metadata dictionary can be used to standardize the variables across all medical conditions | Validate and translate the CDEs xlsx file to JSON format |
| **Tools** | MIP-DQC Tool | | MIP-DQC Tool | MIP-DQC Tool & MIP Data Catalogue |


***Table 3*: MIP Data cleaning, validation, and upload and available Tools**
|| **1srt step** | **2nd step** | **3rd step** |
| --- | --- | --- | --- |
| **Tasks** | Check the dataset csv file quality against the CDEs | Perform the data cleaning and validation | Upload of the dataset csv file on the local node |
| **Tools** | MIP-DQC Tool | MIP-DQC Tool |

![The MIP data flow](https://github.com/HBPMedical/mip-docs/blob/master/images/The%20MIP%20Data%20flow.jpg)

## Extraction and compilation of clinical data as a csv file

### Extract variables from the Electronic Health Record (EHR) system

A dataset that can be uploaded on the local node is a unique csv file that contains all the variables. The first step is hence to extract the clinical data of interest from the EHR system to a csv file. In most cases, a hospital EHR system contains various examination results that a patient obtains during one or more hospital visits. To keep this information, the csv file must contain:

- a field with a unique ID for each PATIENT
- a field with a unique ID for each VISIT
- a "Number of month since first visit" field for each VISIT

In terms of csv file structure, the following basic conditions must be met:

- Header (variable) names must:
  - not contain special characters like space, parentheses, hyphen, etc.
  - use only underscore ("\_") for word separation.
  - not start with any number character.
- The delimiter must be the comma character (",").
- The encoding must be ASCII.

### Extract Imaging Features from MRIs - OPTIONAL

Not all medical conditions require data extracted from Brain Scans (or MRIs) which explains why this step can be skipped. However, because the MIP recognizes only one csv data format, features from MRI images must be extracted and merged to the csv file that contains EHR variables in case they are valuable for the scientific analysis objectives.

Although multiple methodologies can be used to extract those features, we highly recommend following the Statistical Parametric Mapping SPM12 pipeline to harmonize the methodology across the hospitals.

*To simplify the process of feature extraction, you can use the **MRI parallel neuromorphometrics pipeline** that was deployed by the MIP data management team. It is a python wrapper to run the Statistical Parametric Mapping SPM12 pipeline in parallel with Matlab over multiple CPU cores.*

As soon as all variables are merged in a unique csv file, you can proceed with the definition of the Common Data Elements for your medical condition and your scientific analysis objectives.

## Definition of Common Data Elements for a medical condition

### Data Model (Metadata) xlsx File format

Hospitals that want to upload a dataset on the MIP need first to create the Data Model (Metadata) of its dataset.

The Data Model xlsx file contains information about the hospital variables. It corresponds to a table that lists the variables present in the hospital data set and describes them. A template can be downloaded from the Data Catalogue web-based application.

The descriptions required are listed below; in **bold** the ones that cannot be left empty:

- **name** : The full name of the variable
- **code** : The code version of the variable name
- **type** : Format of the variable. Four formats are recognized in the MIP – nominal, date, real and integer.
- **values** : Only for the nominal format. It lists all the levels of the nominal variable with the correspondence between the code and the value. The format used is - {"Code","Value"},{"Code","Value"}. For example, the sex variable is coded as: {"M","Male"},{"F","Female"}.
- unit: Only for real and integer. Unit of the variable (_e.g.,_ km/h)
- canBeNull: Mention with yes/no the possibility of this variable to be null. It is mainly useful for MIP federated nodes.
- description: A precise description of the variable.
- comments: Any comment. For example, a linkage with another variable.
- **conceptPath** : Hierarchy of the variable within the dataset as MedicalCondition/Section/Sub-section/Sub-sub-section etc… This allows the MIP-Front end to create hierarchy visualization of the data. There is no specific number of hierarchy levels required and can be customized to a specific Data Model.
- methodology: Specification of the methodology followed to obtain this variable when different methodologies exist.

!NOTE : Although the semantics and the conceptPath can be customized to a specific Data Model, we highly recommend following existing Standards such as HL7 FHIR, SNOMED or ICD-10

*The **Data Quality Control Tool** allows you to infer this Data Model xlsx file based on your data csv file. In the infer option section of the Data Quality Control Tool, indicate the number of rows that the tool will be based on for the schema inference and the maximum number of categories that a nominal variable can have. You can also include the MIP metadata dictionary to infer the global conceptPath directly for your data.*

### Common Data Elements

Based on the Data Model, a hospital selects the variables that will be made available on the MIP by keeping only the selected variables in the Data Model xlsx file. The CDE file must be named as: "Medical Condition"\_cdes\_"version" (e.g. "dementia\_cdes\_v6").

In case of a MIP-Federated node, three more steps are required:

- Each variable that could lead to identification of a patient must be deleted (i.e., name, date of birth, address…) and must be replaced by a patient code. Only the data controller has access to the table of correspondence code/patient identity.
- Each hospital that is part of the federation needs to agree on the list of the variables AND on the harmonization of each variable. Indeed, variables from each hospital need to have the exact same codification and meaning for nominal variables and, should have been acquired with a similar methodology to be federated. Here is a list of discussion points:
  - Agreement on the Variable list
  - For each nominal variable, agreement of codification and meaning of this codification
  - For each real and integer variable, agreement of the unit and range
  - For each variable, agreement of the methodology followed to acquire it

- Add a nominal variable named "Dataset" that have a level for each hospital federated. A code for each hospital needs to be created (e.g. Centre Hospitalier Universitaire Vaudois is coded chuv and is written as {"chuv"," Centre Hospitalier Universitaire Vaudois "}

As soon as the CDE is defined, and in the same xlsx format as the Data Model, it can be translated to the json format that is the standard format of the MIP. To do so, you can use the Data Quality Control Tool to have first a validation control to avoid any mistake and second translate it to json format. If you are part of a federation you can do it through the Data Catalogue.

*The **Data Quality Control Tool** allows you to validate your Data Model or CDEs to avoid missing cells, extra space etc… . In the Validate DC Excel section of the Data Quality Control Tool, upload your Data Model or CDEs in xlsx format and click on Validate. In case there is no mistake, you can translate it automatically to json format. This translation is also made by **the Data Catalogue** web-based application.*

Once the CDEs have been defined, the process of preparing hospital data for ingestion to the MIP can be started.

!NOTE: In case a hospital wants to join an existing federation, it should download the pre-defined CDEs from the Data Catalogue web-based application and contact the federation leader to be able to join the federation (see already existing federations and medical conditions available on the MIP in the following sub-sections of this document).

### Supported Federations and their associated Medical Conditions as of February 2023

Each CDE associated with a Medical Condition within a federation of hospitals is under the responsibility of a "Federation Leader". The role of the "Federation Leader" is to ensure that the CDE of a Medical Condition evolves over time in a coordinated and versioned manner. The table below gives an initial view of all existing Medical Conditions with the corresponding versions of CDEs and the leader contact in use as of February 2023. For updated information about the available defined medical conditions, please refer to the Data Catalogue web-based application.

 ***Table 4*: MIP-Federated node**

| **Medical Conditions** | **Leader contact** | **Hospital** | **CDE version** |
| :--- | :--- | :--- | :--- |
| Dementia | Dr Thibaud Lebouvier (from 1 November 2021) [Thibaud.LEBOUVIER@chu-lille.fr](mailto:Thibaud.LEBOUVIER@chu-lille.fr)| CHRU Lille | V5 |
| Traumatic Brain Injury (TBI) | Dottore Guido Bertolini [guido.bertolini@marionegri.it](mailto:guido.bertolini@marionegri.it) Stefano Finazzi [stefano.finazzi@marionegri.it](mailto:stefano.finazzi@marionegri.it) | Hospedale Mario Negri, Bergamo, Italy | V8 |
| Mental Health | Prof. Pegah Sarkheil [psarkheil@ukaachen.de](mailto:psarkheil@ukaachen.de) | University Hospital RWTH, Aachen | V8 |
| Epilepsy | Prof. Philippe Ryvlin [Philippe.Ryvlin@chuv.ch](mailto:Philippe.Ryvlin@chuv.ch) | Neurosciences Department, CHUV, Lausanne | V9 |
| NeuroNet | Lewis Killin [lkillin@synapse-managers.com](mailto:lkillin@synapse-managers.com) | SYNAPSE Research Management Partners S.L. | V1 |
| _Stroke (upcoming)_ |
 
## Data cleaning, validation, and upload

### Check of the dataset quality against the CDEs

Based on the CDEs defined is the previous steps, the dataset compiled as a csv, needs to be cleaned/modified and validated according to the definition of all variables. The two main violation types that need to be fixed are:
- Constraint violations which regroup:
  - minimum (for date, integer, numerical)
  - maximum (for date, integer, numerical)
  - enum (list of enumerations for nominal datatypes)
- Datatype violations: Case when a value in a column has a different datatype than the one that has been declared for that variable in the CDEs. This also includes the empty cells that should be truly empty and not with "NA", "Nas", "unknowns" etc…

### Perform the data cleaning and validation

All violations highlighted before should be corrected so that each variable present in the csv file, corresponds to the one listed in the CDEs. Be careful to save the csv file in the correct format, which is csv; encoding must be ASCII with comma separation.

### Data set upload

To become visible to the MIP end users, the dataset csv must be first renamed as the hospital code defined on the Dataset variable created on the CDE (e.g., "chuv.csv"). The file is then copied to the corresponding "medical condition" folder on the MIP local node and, when the hospital is part of a federation (federated hospital), to the corresponding "medical condition" folder on the MIP federated node.

*The **Data Quality Control Tool** allows you to compare the CDEs json file with your dataset csv file to highlight the violations and suggests possible corrections. If the corrections suggestions are good, the DQC tool can also perform those corrections and save the corrected dataset in the correct format. In case you want to join an existing federation, the DQC tool allows you to perform a data mapping, which transforms the hospital's local variables to a set of variables of a target CDEs medical condition.*
