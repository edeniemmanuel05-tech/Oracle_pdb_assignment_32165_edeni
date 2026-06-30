# Individual Assignment II: Oracle Pluggable Database (PDB) Administration

## 1. Assignment Overview
This assignment covers the hands-on implementation of Oracle Multitenant Architecture, focusing on configuring Pluggable Databases (PDBs), administration privileges, user schema setups, and lifecycle management within a Container Database (CDB).

## 2. Oracle Environment Details
- **Oracle Database Version:** Oracle Database 121c Enterprise Edition
- **Operating System:**  Windows 11
- **Tools Used:** SQL*Plus Command Line Interface, Oracle Enterprise Manager (OEM) Express

## 3. Task Documentation

### Task 1: Persistent PDB Creation & User Configuration
- **PDB Name:** `ed_pdb_32165`
- **Configured Username:** `edeni_plsqlauca_32165`
- **Execution Workflow:** The database container was deployed from the seed database using `FILE_NAME_CONVERT`. The PDB container status was safely adjusted to `READ WRITE`, structural sessions were redirected, and administrative `DBA` roles were mapped cleanly to the permanent user schema.

### Task 2: Temporary PDB Lifecycle Management
- **Temporary PDB Name:** `ed_to_delete_pdb_32165`
- **Execution Workflow:** Implemented isolated database initialization testing. Verified the operational mount framework, changed the state to active execution, gracefully terminated all active background connections, and executed a complete absolute purge using the `DROP PLUGGABLE DATABASE ... INCLUDING DATAFILES` statement to clear storage allocations.

### Task 3: Oracle Enterprise Manager (OEM) Configuration
- Successfully logged into the unified OEM Dashboard workspace to inspect container performance, system parameter flags, active listener properties, and verified the valid operations of `ed_pdb_32165`.

---

## 4. Challenges and Solutions
- **Challenge:** Encountered `ORA-65049: creation of local user or role is not allowed in root container` during initialization.
- **Solution:** Successfully altered the context state container using `ALTER SESSION SET CONTAINER = ed_pdb_32165;` before executing administrative account creation scripts.

## 5. Lessons Learned
- Gained fundamental technical experience with Pluggable Database lifecycles, user access provisioning controls, structural isolation, and clean workspace deletion within multitenant container design frameworks.

## 6. Integrity Statement
"I confirm that this assignment represents my own practical work, screenshots, and documentation. All external resources consulted have been properly acknowledged."
