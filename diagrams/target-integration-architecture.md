# Target Integration Architecture

This editable diagram shows alternative planning landscapes and the shared business touchpoints. The alternatives are not intended to imply that every component exists in a single deployment.

~~~mermaid
flowchart LR
    EXT[External partners<br/>Suppliers, customers, carriers]
    EXEC[Transactional execution<br/>MM, PP, IM, QM, SD]
    CHOICE{Planning landscape?}
    APO[Separate SAP APO PP/DS]
    CIF[Configured ERP–APO CIF flow]
    S4[Embedded SAP S/4HANA PP/DS<br/>where deployed]
    WH[Warehouse execution<br/>EWM / warehouse processes]
    TM[Transportation planning<br/>TM / carrier events]
    MON[Cross-functional monitoring<br/>Queues, acknowledgements, ageing]
    BIZ[Business reconciliation<br/>Stock, orders, delivery and freight status]

    EXT <--> EXEC
    EXEC --> CHOICE
    CHOICE -->|Legacy landscape| CIF
    CIF <--> APO
    CHOICE -->|S/4HANA landscape| S4
    EXEC <--> WH
    EXEC <--> TM
    APO --> MON
    S4 --> MON
    WH --> MON
    TM --> MON
    MON --> BIZ
    BIZ --> EXEC
~~~

## Reading notes

- In a legacy ERP plus separate SAP APO landscape, CIF is the documented integration pattern referenced by the report. Transfer scope and configuration depend on the implementation.
- In an S/4HANA landscape, PP/DS may be embedded. Do not apply a legacy APO/CIF blueprint without confirming the product architecture.
- Warehouse and transportation event exchange depends on the specific EWM/TM deployment, integration design, and release.
- Technical acknowledgement is not sufficient by itself: the receiving business function must verify the resulting stock, order, delivery, or freight state.
