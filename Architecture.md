
## Medical Informatics Platform Architecture

The Medical Informatics Platform is a complex information system comprising numerous software components designed and integrated by different SP8 partners. In this chapter we present the logical architecture of the MIP, depicting some of its key characteristics and major building blocks. This description does not aim to be a detailed listing of all the software components produced to compose the MIP. It rather aims to assist in understanding the overall structure and interdependencies between the major services that comprise the MIP.

The following diagram Figure 1 - Overall Architecture, sketches at a very high level the overall architecture of the MIP. 

![Overall Architecture](/images/architecture.png)
**Figure 1: Overall Architecture**

The MIP is architected following an N-Tier paradigm. Multiple tiers are identified within the platform to allow for a clear separation of domains and to provide reusability and separation of concerns between the business and technology layers of the overall platform. Additionally, the various service offerings of the platform are provided following the microservice paradigm, where applies and constitutes a value adding proposition.

- The **portal** acts as the main entry point to the business offerings of the MIP for researchers and clinicians
- The **API layer** offers a protected layer of functionality exposed in a uniform and interoperable manner
- The **API layer** acts as a gateway to the MIP offerings, providing horizontal reuse, vertical specialization and separation of concerns and technological restrictions through the employment of a microservices architecture
- For the **authentication** mechanisms proven standards are reused to allow for a wide range of interoperability between the authenticated clients and the platform services
- A set of **operational data** assist in the streamlined communication and interaction between the clients and the MIP services
- The **Data Factory** set of services facilitate the ingestion of hospital data within the MIP
- The **deployment** stack of the MIP can be split to facilitate disjoint but complementary deployments

- **MIP Local** offers enhanced services and analytical capabilities within the boundaries of each hospital
- **MIP Federated** offers federated analysis over anonymized data, across multiple hospitals

In the following diagram Figure 2 - Data Factory, the data flow and logical architecture of the Data Factory pipeline is highlighted.

![Data Factory](/images/data_factory.png)
**Figure 2: Data Factory**

- The initial hospital data, including both electronic health records as well as brain scan data, go through a process of pseudonymization and are injected into the MIP pipeline.
- A set of Quality Control tools are utilized throughout the process to ensure the validity and compliance of the data
- A number of extension points to external systems (Blue Brain Nexus Knowledge Graph) and value adding tooling within the MIP (LORIS) are identified and can be hooked in the pipeline through appropriate connector modules
- Underpinning tools are utilized for the extraction of brain features as well as the mapping of the ingested data to the MIP data model
- The harmonization process builds up the canonical model that subsequent MIP operate on
- The anonymization module makes sure that the data it processes cannot be linked back to its input and makes them available for federated processing
- The output of the process is propagated to the subsequent MIP platform components that exposes it for analysis, depending on the MIP mode of operation
  - Local analysis – Access and analysis over hospital local data
  - Federated analysis – Controlled access and federated analysis over multi-hospital data
-

To facilitate the dual mode of operation, the MIP offers a different deployment stack so that hospitals can opt-in to the federated processing capabilities offered. The following diagram, Figure 3 - Local vs Federated Analysis, depicts the architecture and processing flow between the different modes of analysis offered.

![Local vs Federated Analysis](/images/local_federated_analysis.png)
**Figure 3: Local vs Federated Analysis**

Depending on the mode of operation, different hospitals may operate on a single &quot;Local analysis&quot; mode, or they can also participate in federation, providing their data for federated analysis.

•The **analytical capabilities** are offered to authenticated and authorized users of the MIP

•The **API Gateway** offers a uniform and homogenized handling interface to the analytical capabilities

•The **Portal** presents and assists the user to perform the needed experiments

•The **Analysis Stack** along with the Resource Management Stack hide the complexity involved on performing the requested experiment

•The **Algorithm Library** offers the toolbox from which the users can select the required processing

•Depending on the mode of analysis, local or federated, the respective analysis engine will handle the appropriate communication and push the analysis within the needed boundaries

•In the case of federated analysis, the required privacy compliance will be applied at the boundaries of each contributing hospital

In the following diagram, Figure 4 - Algorithm Factory, some more details are given on the architecture and interactions between the components that underpin the analytical capabilities of the MIP.

![Algorithm Factory](/images/algorithm_factory.png)
**Figure 4: Algorithm Factory**

Within each hospital, depending on the mode of analysis, local or federated, the set of available clinical data, pseudonymized or anonymized, are available for the analytical module to operate on:

•The metadata that describe the available dataset and exposed canonical model is used to build and evaluate the model requested

•The **Dataset**** catalogue** is used to drive the evaluation of the experiment within the appropriate boundaries

•The **API Gateway** interface exposes a uniform layer of interacting with the analytical flows

•The **Analysis**** Stack** contains all the required components that will assist in formulating the experiment, compose the runtime environment for its evaluation and stage its execution

•Depending on the semantics and requirements of the experiment evaluation, the appropriate **analysis engine** is utilized, and the needed resources are scheduled and employed

•The experiment configuration, runtime data, transient sets and results are stored within the context of the experiment

Exposing the functionality of the MIP but also enhancing it through the appropriate user experience and integrations with external services and tooling, the MIP Portal acts as the entry point to the MIP offerings. The following diagram, Figure 5 - Portal, depicts the main functional areas that the MIP Portal offers and its interactions within the MIP architecture layers.

![Portal](/images/portal.png)
**Figure 5: Portal**

•The **Analytics** area is responsible to assist the user compose the model of the analysis, define the experiment to be evaluated, visualize the outcome of the analysis and define the means of collaboration through which this analysis can be further used by researchers and clinicians

•Through the **Data Exploration** area, the user can browse the available Datasets, define the model and schema of the data exposed by the respective datasets through the Data Catalogue, visualize the metadata available for the canonical model

•The **authentication** of the MIP user is performed through appropriate workflows assisted by the portal and the view presented to the user is tailored to the authorization the user is granted

•Several **additional tools** can be made available to the user depending on his roles and functions within the MIP and the available extensions offered through the Portal, such as Workflow Editor, a LORIS User Interface, integrations with The Virtual Brain and SEEG MIP.
