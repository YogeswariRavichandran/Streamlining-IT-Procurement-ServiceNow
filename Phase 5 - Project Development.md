# Phase 5: Project Development

## Flow Creation Steps
1. Open **Flow Designer** in ServiceNow.
2. Create Flow: 
   * **Name:** `Standard laptop task`
   * **Application:** `Global`
   * **Run as:** `System User`
3. **Add Trigger:** `Service Catalog`.
4. **Add Action:** `Create Catalog Task`.
   * **Target:** Requested Item Record
   * **Short Description & Description:** `Laptop need to Configured`
   * **Assignment Group:** `Hardware`
   * **Approval Status:** `Approved`
5. **Activate** the Flow.
6. Map the Flow under **Maintain Items** ➔ **Standard Laptop** ➔ **Process Engine**.
