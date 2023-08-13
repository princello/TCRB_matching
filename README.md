# TCRB_matching

---

## **GitHub Introduction: TCR Sequencing Data Processing**

This repository contains scripts and functions designed to process, analyze, and link T-cell receptor (TCR) sequencing data. The focus is on comparing data generated from 10X Genomics TCR sequencing and Adaptive TRB sequencing to extract meaningful insights from TCR sequences.

### **Data Overview:**
1. **10X TCR Sequencing Data**:
   - Includes columns like 'barcode', 'chain', 'v_gene', 'j_gene', and 'raw_consensus_id'.
   - Important for understanding individual T-cell clones.

2. **Adaptive TRB Sequencing Data**:
   - Contains fields such as 'v_resolved', 'j_resolved', 'rearrangement', 'amino_acid', and 'productive_frequency'.
   - Useful for a broader view of the T-cell repertoire.

### **Key Functions:**

1. **`treatcr(tenx_data)`**: Processes 10X TCR sequencing data, filtering on 'TRB' chains, ensuring the V and J regions are identifiable, categorizing these regions, and counting TCR clonotypes.

2. **`treathvg(adap_data, sample_name='', labeled_trb=[])`**: Handles the Adaptive TRB sequencing data. Depending on the provided parameters, this function can focus on specific samples or labeled TCR sequences and categorizes the V and J regions.

3. **`link(tcr_data, hvg_data, level=1)`**: Links the processed data from the first two functions based on either the V and J gene families (level 1) or includes their subtypes (level 2). 

### **Workflow**:
1. Process the 10X TCR sequencing data with `treatcr`.
2. Process the Adaptive TRB sequencing data using `treathvg`.
3. Establish a connection between the two processed datasets using `link`, culminating in the final linked dataset: `tcr_sel`.

### **Purpose**:
The code enables a comprehensive comparison and integration of 10X TCR sequencing data with Adaptive TRB sequencing data, emphasizing relevant T-cell receptor sequences and their characteristics.

---
