# Supplier-Delay Workflow

This diagram follows the illustrative 24-hour supplier delay and highlights the decisions that should occur before production and dispatch dates are communicated.

~~~mermaid
flowchart TD
    A[Supplier advises 62,000-pouch delivery delay] --> B[Buyer validates supplier, PO item, quantity and new date]
    B --> C[Update purchasing confirmation / source record]
    C --> D{Destination acknowledgement received?}
    D -->|No| E[Create visible exception with owner and age]
    E --> F[Correct mapping or retry transient failure safely]
    F --> C
    D -->|Yes| G[Planning recalculates material availability]
    G --> H[Flag temporary 31-tonne-equivalent pouch gap]
    H --> I[Review and sequence the 107.5 tonnes equivalent supported by opening stock]
    I --> J[Check due dates, quality, resource capacity and other components]
    J --> K[Notify sales of at-risk order dates]
    K --> L[Warehouse and transport recheck readiness and planned loads]
    L --> M[Supplier receipt arrives in the scenario]
    M --> N[Post receipt and apply required quality release]
    N --> O[Recheck the remaining quantity and revised schedule]
    O --> P[Reconcile delivery, warehouse, freight and customer promise]
    P --> Q[Close with evidence and monitor the outcome]
~~~

## Core scenario arithmetic

- Weekly demand: 138.5 tonnes.
- At 2,000 pouches per tonne, modeled requirement: 277,000 pouches.
- Opening pouch stock: 215,000 pieces, equivalent to 107.5 tonnes under the simplified assumption.
- Delayed receipt: 62,000 pieces, equivalent to 31.0 tonnes.
- Do not treat incoming stock as usable until the required receipt and quality rules are satisfied.

The shared-pouch calculation is a scenario simplification. Real product-specific pouches and labels must remain distinct in SKU-level BOM and master-data design.
