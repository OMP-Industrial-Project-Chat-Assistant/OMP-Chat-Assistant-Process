# Introduction

**Version:** 1.0

**Last Edit:** 12.05.2025

**Last Editor:** Vagif Khalilov

**Owner:** Vagif Khalilov

**Approval Status:** N/A

**Type:** Process

**Description:** This document describes all the procedures associated with Defect Management Process

**Dependencies:**
- Source code
- Architectural Design

# Justifications
- Requirement assurance procedures must be properly documented per [Innopolis University needs](</Context and Requirements Management/EN/Context/Business Context.md>)
- Requirement assurance procedures are needed to satisfy the outlined [requirements](</Context and Requirements Management/EN/Requirements/Software Product Requirements.md>)
Here's the revised **Defect Management Process** using GitHub-centric tooling (no Jira/Confluence), tailored for your dual-repo setup (code + docs):

---

# Defect Management Process  
*GitHub-Centric Workflow for Aurora OS Chatbot*

---

## 1. Tools & Repositories  
| Purpose | Repository | Artifacts                                      |  
|---------|------------|------------------------------------------------|  
| **Code Defects** | `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process` | Issues, Pull Requests, `bug`, `wontfix` labels |  
| **Documentation Defects** | `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process` | Issues, `bug`, `wontfix` labels                |  

---

## 2. Defect Lifecycle  

### **1. Identification**  
**Where:** GitHub Issues in respective repo  
**Template:**  
```markdown
**Defect Type**: [Performance/Language/Docs]  
**Severity**: S1/S2/S3 (see below)  
**Repro Steps**:  
1. Query: "..."  
2. Actual: GPU usage 17.2GB  
3. Expected: ≤14.4GB per formula  

**Environment**:  
- AuroraOS Doc Version: 5.1.1-20240520  
- Model: `some-llm`  

**Evidence**:  
- `nvidia-smi` logs attached  
- Screenshot of Grafana (120s timeout)  
```

---

### **2. Triage**  
**Roles**:  
- **Code Defects**: Developer 
- **Docs Defects**: Developer, Customer 

**Process**:  

1. Priority assignment:  
   ```markdown
   /priority <S1|S2|S3>  
   /assign @developer-handle
   ```

**Severity Criteria**:  

| Label | Response SLA | GPU Impact |  
|-------|--------------|------------|  
| `S1` | >2min response | >14.4GB memory |  
| `S2` | Incorrect Russian | Broken doc links |
| `S3` | Cosmetic issues |  |

---

### **3. Fix Development**  
**Branch Naming Convention**:  
```bash
git checkout -b bug/{[chat/process]-#}/shortdesc
# Example: bug/chat-45/gpu-leak
```

**Code Requirements**:  
1. Must reference issue
2. Include verification test:

**Docs Requirements**:  
- Updates go to `https://github.com/OMP-Industrial-Project-Chat-Assistant/OMP-Chat-Assistant-Process/issues/{#}`

---

### **4. Verification**  
**Automated Checks**:  
- By running tests-job in CI.

**Manual Steps**:  
1. Assign to some of developer
2. Approve via PR review with:  
   ```diff
   + Verified: GPU memory now 12.8GB (issue #45)
   ```

---

### **5. Closure**  
**Requirements**:  
1. All checks pass  
2. Issue linked to PR  
3. Docs updated (for S1/S2)

---

# Changelog
- v1.0 12/05/2025 - conversion of document to current format by Vagif Khalilov
