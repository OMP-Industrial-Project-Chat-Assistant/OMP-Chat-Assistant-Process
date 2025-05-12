# Introduction

**Version:** 1.5

**Last Edit:** 13.04.2025

**Last Editor:** Yaroslav Kim

**Owner:** Vagif Khalilov

**Approval Status:** Reviewed by Yaroslav Kim

**Type:** Process

**Description:** This document describes all the procedures associated with maintaining Functional Suitability

**Dependencies:**
- [Requirements](/Context%20and%20Requirements%20Management/EN/Requirements/Software%20Product%20Requirements.md)
- [Business Context](/Context%20and%20Requirements%20Management/EN/Context/Business%20Context.md)

# Justifications
- Requirement assurance procedures must be properly documented per [Innopolis University needs](</Context and Requirements Management/EN/Context/Business Context.md>)
- Requirement assurance procedures are needed to satisfy the outlined [requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)

# Quality Requirement Assurance Plan: Maintainability

## Quality Requirement Description

This characteristic represents the degree of effectiveness and efficiency with which a product or system can be modified to improve it, correct it or adapt it to changes in environment, and in requirements.

---

# Quality Requirement Assurance Plan: Maintainability  
*Aligned with ISO25010 and Business Constraints*

---

## **Activity 1: Architectural Modularity Assurance**  
**Source:** Ensure ease of product development
**Triggers:**  
- Report of cascading failures after a module change  
- Aurora OS documentation version update requiring integration  

### **Training Required**  
1. **SOLID Principles**: To enforce decoupled, single-responsibility modules.
2. **Chaos Testing**: To validate failure isolation (critical for GPU-bound systems).  

### **Measurements**  
| Metric | Target | Measurement Method |  
|--------|--------|--------------------|  
| Cross-module failure rate | 0% | Automated integration tests post-change |  
| Dependency depth | ≤2 layers | SonarQube dependency analysis |  
| Interface stability | ≥90% unchanged APIs | API spec version diff |  

### **Tools**  
1. **Draw.io**: Collaborative diagramming to visualize/modify architecture (supports real-time team edits).  
2. **SonarQube**: Static analysis for circular dependencies/module coupling.  
3. **Testcontainers**: Isolated testing of module interactions.  

### **Entry Criteria**  
- Incident tracker reports **≥2 unrelated component failures** caused by a single module change.  
- SonarQube flags **>3 circular dependencies** in a module.  

### **Effort Estimation**  
- Minor refactor: **3 story points** 
- Major redesign: **12 story points**   

### **Time-to-Resolution**  
- Estimated by lead developer based on sprint capacity.  

### **Procedure**  
1. **Triage**:  
   - Assign issue in github with description.    
2. **Analysis**:  
   - Run `sonar-scanner --dependency-check`.  
   - Generate dependency graph via `draw.io`.  
3. **Redesign**:  
   - Define new interfaces.  
   - Conduct peer review with another developer.  
4. **Testing**:  
   - Deploy to `test` environment with chaos monkey (random module failures).  
   - Validate isolation via `pytest -m "integration"`.  
5. **Documentation**:  
   - Update `Architectural Design/Architecture.md` with revised diagrams.    

### **Artifacts**  
- **Input**: Incident report, SonarQube analysis  
- **Output**: Updates contracts between modules, Chaos test results, Update diagrams in `Architectural Management` folder  

### **Exit Criteria**  
- **Zero** cross-module failures in 72 hours of chaos testing.
- SonarQube score **≥A** for module independence.
- Approval by 3/4 developers.

---


# Changelog
- v1.3 13/04/2025 - conversion of document to current format by Yaroslav Kim
- v1.4 12/05/2025 - update by Vagif Khalilov
- v1.5 12/05/2025 - review and updates by Yaroslav Kim
