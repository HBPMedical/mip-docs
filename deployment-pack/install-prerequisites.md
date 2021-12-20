# Installation Prerequisites and Installation Guide

Preamble
--------

> This document provides participating hospitals and institutions with a
> description of the pre-requisites necessary to install the MIP
> components, and how to interact with the MIP operations team to build
> a running MIP. It forms part of the Deployment Pack standard document
> set that also includes the following additional documents:

-   [Executive Summary](./deployment-pack/executive-summary.md)
-   [Installation and License Agreement (PDF)](./docs/MIP_Installation_and_License_Agreement_-_V02.10_210c5d6538.pdf)
-   [Ethics and Legal Requirements](./deployment-pack/ethics-legal.md)

Assumptions
-----------

-   The MIP is to be installed for the first time at Hospital site, OR
    an earlier version of MIP has been installed at Hospital and will be
    replaced or upgraded

-   The MIP Installation and License Agreement document is read and
    understood, and the necessary signatures are in place

-   The onsite deployment team has read the MIP Executive Summary, which
    includes a high level description of the MIP and explains the key
    steps in the MIP deployment process

-   The hospital MIP technical and user community has access to the MIP
    User Guide and the Data Factory User Guide

-   All necessary hardware and software for the planned deployment will
    be installed and available before the MIP Operations team is
    involved. Please note, in order to ensure a smooth installation it
    is important that the preparation is executed exactly as described
    in the requirements that follow

-   The hospital team understands that the MIP can be progressively
    installed, over time. Starting with MIP Local, using demonstration
    and/or hospital data for local use only, then adding the MIP
    Federated node if required, and making Hospital ANONYMIZED data
    available to the "Medical Condition" based federation of choice

-   When the Hospital joins or is part of a Medical Condition based
    federation the Hospital adopts the data model defined by the
    federation. The federation defines the common data model in
    collaboration with other hospitals and subject matter experts

-   The hospital's data shall be prepared and pre-processed by the
    hospital team following the Data Factory use guide, so that data are
    in the correct format for import / upload to the MIP

-   The MIP operations team will accompany the Hospital team in the
    process of preparing for and setting up the MIP until the MIP is
    deemed operational

-   The MIP operations team is NOT in charge of the MIP Installation and
    set-up, nor responsible for all or part of the MIP application
    installation and Hospital data preprocessing, nor the quality of
    Hospital data

Contacts
--------

Communications, coordination and deployment:

-   Name

-   Email

-   Telephone


Technical support (MIP operations team):

-   Name

-   Email

-   Telephone

Installation Pre-requisites
---------------------------

> There are three elements to a full MIP deployment: MIP Local, MIP
> Federated and the Data Factory. In order to deploy the MIP the
> following hardware and software is a prerequisite to installation, and
> must be available before the MIP operations team is involved.



> **MIP Local Node**
>
> This is the most common deployment, and is a "stand-alone" mode. The
> initial deployment will allow you to try the MIP with test data and
> import and analyse your own data.

| Server|
--------
| Single core |
| 4GB RAM |
| 16GB HDD |

|OS|
----
|Ubuntu 20.04|

> **MIP Federated Node**
>
> In order to participate in a federation and allow analysis of your
> data by other researchers, a second server is required. Before your
> data is imported to the federated node it passes through an
> anonymization process (see the Data Factory user guide).

| Server|
--------
| Single core |
| 4GB RAM |
| 16GB HDD |

|OS|
----
|Ubuntu 20.04|

> The two servers can be either separate, physical machines or virtual
> machines. The machines need to be "clean" with no software running
> other than that specified. Any exception to this can cause unexpected
> problems and delays with the installation.
>
> In both cases, physical and virtual, there is strict security between
> the machines, and no possibility of researchers from another
> institution having access to your non-anonymised data. Please note
> that during analysis in a federation your data never leaves you
> physical location.
>
>  
>
> For a federated deployment there are some connectivity requirements
> that the MIP operations team will supply during collaboration to
> deploy your MIP. In all cases, SSH access (TCP/22) will be required to
> support the deployment. Deployment options for CentOS and RHEL are
> being considered.
>
>  

> **Data Factory**
>
> For a complete MIP installation, and to aid preparation of your data
> for use with the MIP you will need to install the Data Factory. The
> Data Factory includes the data anonymisation module.

| Server|
--------
| Single core |
| 4GB RAM |
| 16GB HDD |

|OS|
----
|Ubuntu 20.04|

> Once you have fulfilled these pre-requisites according to the MIP you
> plan to deploy, contact the MIP operations team for support with the
> next steps.

Schematic Diagram
-----------------

![](media/image5.png)

Check List
----------

| Check List                                                                        | No | Yes |
|-----------------------------------------------------------------------------------|----|-----|
| *Initial deployment*                                                           |    |     |
| Are the necessary agreements ready, approved and signed?                          |    |     |
| Are the necessary resources assigned and available for the project?               |    |     |
| Is the project objective clear \- MIP Local only, or MIP Local plus MIP Federated? |    |     |
| Is the necessary hardware and operating system installed and available?           |    |     |
| Is the remote access for the MIP operations team in place and accessible?         |    |     |
| *Prepare for use*                                                             |   |    |
| Is the hospital data prepared for import/upload to the MIP Local?                 |    |     |
| Is the hospital data prepared for import/upload to the MIP Federated?             |    |     |
| (See Data Factory user guide)                                                     |    |     |
| Has the MIP user community followed the training video series?                    |    |     |

***

***