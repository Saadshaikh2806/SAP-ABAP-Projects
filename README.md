# Sales Order Interactive ALV Report

## 📋 Project Overview
**Objective:** Developed a comprehensive ALV report to track Sales Orders by Sales Organization, Customer, Date, and Order Type. This tool helps the sales team quickly analyze daily booking data without running standard T-Codes.

## 📸 Output Screenshots

### 1. Selection Screen (Input)
*User filters data by Sales Org, Date Range, Order Type, or Customer Number.*
![Selection Screen](Alv1.png)

### 2. ALV Grid Output (Result)
*Displays joined data from VBAK (Header), VBAP (Item), and KNA1 (Customer).*
![ALV Output](Alv2.png)

## 🛠 Technical Highlights
* **ALV Framework:** Utilized the function module `REUSE_ALV_GRID_DISPLAY` for standard grid output.
* **Data Retrieval:** Implemented an efficient **`INNER JOIN`** on tables `VBAK` (Header), `VBAP` (Item), and `KNA1` (Customer) to fetch data in a single database hit.
* **Modularization:** Code structure organized using **Subroutines (`FORM`/`ENDFORM`)** for data selection, field catalog building, and display logic.
* **Field Catalog:** Created a dynamic **Macro** (`DEFINE ADD_FIELD`) to build the field catalog manually, reducing code redundancy.

### 💻 Code Snippet: Field Catalog Macro
*Implemented a macro to streamline column definition:*
```abap
  DEFINE ADD_FIELD.
    WA_FIELDCAT-FIELDNAME = &1.
    WA_FIELDCAT-SELTEXT_M = &2.
    WA_FIELDCAT-COL_POS   = &3.
    APPEND WA_FIELDCAT TO IT_FIELDCAT.
    CLEAR WA_FIELDCAT.
  END-OF-DEFINITION.
```

---
*Developed by Saad Shaikh | SAP ABAP Fresher*


