Introduction to the MIP
=======================

The main objective of this document is to provide the reader (hospital
or health organization director and decision maker) with an introduction
to the MIP and its capabilities, a description of the benefits that the
MIP offers in terms of research capabilities once deployed within the
organization, and finally outlines how the organization, working with
the MIP deployment and support team, shall proceed to deploy the MIP on
premise.

Introduction
------------

Brain diseases and related medical conditions, considered as a whole,
affect 165 million European citizens, many whom are being at least
partly managed in hospitals. The clinical data collected from these
patients represent a unique source of information for better
understanding and treating brain diseases and related medical conditions
but are unfortunately not usually available for research.

The MIP has been developed by the Human Brain Project, an EU Horizon
2020 Flagship project, in order to facilitate access to clinical data
stored in hospitals for research purpose, while preserving data privacy.
The MIP aims at enabling breakthrough medical progress in the field of
brain diseases and related medical conditions through access to an
unprecedented volume of patient's data.

MIP Description
===============

The MIP is an innovative data analysis and data collection system that
provides an interface for various investigators (clinicians,
neuroscientists, epidemiologists, researchers, health managers) enabling
them to access and analyze anonymized medical data currently locked in
hospital, research centers and public databases, without moving the data
from the hospital where they reside, and without infringing on patient
privacy.

The MIP is designed to help clinicians and researchers aiming to adopt
advanced analytics for diagnosis and research in clinics and to promote
collaborative neuroscience research using hospital data.

MIP 2-Tier Architecture
-----------------------

The MIP has been designed adopting a 2-tier architecture which
guarantees total hospital data protection and privacy by design. The MIP
offers two main solutions, the MIP-Local and the MIP-Federated
instances.

The MIP-Local Node contains anonymized data that can only be
accessed and analyzed by the Local Data Manager and its accredited staff
from within the hospital.

The MIP-Federated Node contains anonymized data and can be connected to
other MIP-Federated Nodes located in other hospitals when the decision
is made to join the MIP Network (medical condition-based federations of
hospitals) and to provide access to hospital data to members of the
network.

Upon signed agreements (between the data provider`s institution and the CHUV), and admission to the MIP
Network, accredited researchers can query multiple MIP federated Nodes
and obtain aggregated results. Queries of the MIP-Federated Nodes does
not allow to copy or upload any data, nor to see individual patient's
data.

The 2-tier MIP architecture (MIP Local, MIP-Federated) has been designed
in order to address the specific challenges of:

-   local deployment adapted to each hospitals' environment,

-   capturing and processing heterogeneous types of data (e.g.
    socio-demographic, clinical, biological and neuroimaging data),

-   fulfilling privacy rules, policies and best practices to enable
    efficient and secure data sharing,

-   harmonizing data through Common Data Elements for cross-site
    comparisons, and

-   integrating readily available statistical and machine learning
    tools.


MIP functionalities
===================

The MIP, after installation at hospital, provides the main components
and end-user functionalities briefly described here after.

Functionality of the Medical Informatics Platform
---

**Components** | **Description** 
---------------|---------------- 
Portal             | The portal acts as the main entry point to the business offerings of the MIP for researchers and clinicians
API Layer          | The API layer offers a protected layer of functionality exposed in a uniform and interoperable manner. It acts as a gateway to the MIP offerings, providing horizontal reuse, vertical specialization and separation of concerns and technological restrictions through the employment of a microservices architecture|
Authentication     | The authentication mechanism uses proven standards to allow for a wide range of interoperability between the authenticated clients and the platform services
Operational data   | A set of operational data assist in the streamlined communication and interaction between the clients and the MIP services
Data Factory       | The Data Factory set of services facilitate the ingestion of hospital data within the MIP
Deployment Stack   | The deployment stack of the MIP can be split to facilitate disjoint but complementary deployments - MIP Local offers enhanced services and analytical capabilities within the boundaries of each hospital - MIP Federated offers federated analysis over anonymized data, across multiple hospitals

**End-user functionality**              | **Description**
----------------------------------------|----------------
Import and analyse local data           | Pseudo-anonymise selected local data sets and run experiments using AI algorithms with the MIP
Join a federation/pathology             | Elect to submit and analyse data for a particular MIP federation
Select and analyse federation variables | Capability to selectively analyse variables for a particular federation
Save & filter variables                 | Filter and save selected variable analyses
Run experiments using AI algorithms     | Select AI algorithms compatible with selected datasets and variables


Key Benefits from being part of the MIP Network
-----------------------------------------------

Since the beginning of the Human Brain Project (HBP) the MIP has been
developed and installed in an increasing number of participating
hospitals. The Lausanne university hospital (CHUV) is the HBP partner
coordination this activity.

A few key benefits to expect from joining the MIP network are the
followings:

-   Participate in the largest ever funded Europe wide brain research
    initiative,

-   Train and use novel state-of-the-art analytical tools, including
    machine learning algorithms,

-   Investigate and discover novel findings from its own data using the
    MIP-Local Node

-   Participate or lead Federated analyses on big data available in the
    network of MIP-Federated Nodes

-   Develop new scientific collaborations

-   Increase the chance of future successful national or European grant
    applications

MIP Deployment Process
======================

The MIP deployment process follows several steps to facilitate the
installation flow and progressively allows the hospital staff to gain
experience along the implementation process (see Figure 2).

The first 5 steps fall within the scope of installing a local version of
the platform -- the MIP-Local -- which allows researchers to compare
their data with the public databases already included in the MIP:

1.  Identify all relevant hospital staff required to proceed to MIP
    deployment and present them the platform and the deployment process.

2.  Secure signature of the MIP Installation Agreement by both the
    Hospital and CHUV legal representatives. This agreement covers
    installation of the MIP software, but not data sharing.

3.  Prepare the IT infrastructure (e.g. server) needed to install the
    MIP-Local according to its specifications. This preparation is
    typically performed by the Hospital IT staff with assistance from the CHUV IT team, if needed.

4.  Install the MIP-Local software, usually through a combined effort of
    the Hospital IT staff and the MIP-CHUV deployment team. Part of the
    installation can be performed remotely through VPN connection, if
    required by the Hospital. On site, hospital-specific tuning is often
    required.

5.  Capture pseudonymized patients' data from the
    Hospital or research department aiming to use the MIP, in the MIP-Local , in full
    compliance with all local ethics and regulatory procedures. This
    step is undertaken under the full responsibility of the Hospital or
    research department and its local Data Coordinator. Once data have
    been captured in the MIP-Local, the Local Data Coordinator and his
    accredited local staff can use the MIP to analyse their data. No
    other stakeholder has access to these data.

Thus, researchers have the opportunity to test the MIP and apply its
algorithms to their own datasets in combination with public pre-existing
cohorts. In case they want to create a federation together with other
centres, they have to follow the next steps:

1.  Secure the signature of the MIP Data Sharing Agreement by both the
    Hospital and CHUV legal representatives. This agreement covers the
    possibility to perform federated analyses of fully anonymized data
    captured in the MIP-Federated node of the hospital.

2.  Secure participation of the Local Data Coordinator to the relevant
    MIP DGSC disease-specific board.

3.  Prepare the IT infrastructure (e.g. server) to install the
    MIP-Federated Node software (same procedure as previously described
    in step 3).

4.  Install the MIP-Federated Node software (same procedure as
    previously described in step 4).

5.  Proceed to full anonymization of the data stored in MIP-Local and
    then push these data into the MIP-Federated Node database. This step
    is undertaken under the full responsibility of the Local Data
    Coordinator.

6.  Perform federated analysis.

Contacts
========

For more information you can contact HBP-MIP Leadership team members:

<philipperyvlinhbp@gmail.com>

<erika.borcel@chuv.ch>

***

***
