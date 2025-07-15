# Storage Gateway Model Exam Questions

---
**Q1:** A company wants to back up its on-premises SQL Server database to AWS and enable rapid recovery in case of disaster. Which Storage Gateway type should they use?
- A) File Gateway
- B) Volume Gateway (cached mode)
- C) Tape Gateway
- D) S3 Transfer Acceleration

**Answer:** B. Volume Gateway (cached mode) presents iSCSI block storage and backs up data as EBS snapshots for rapid recovery.

---
**Q2:** An organization needs to replace its physical tape library for long-term, compliant backups. Which AWS service and configuration should they use?
- A) File Gateway with S3 Object Lock
- B) Volume Gateway (stored mode)
- C) Tape Gateway with S3 and Glacier
- D) EFS with lifecycle management

**Answer:** C. Tape Gateway emulates a virtual tape library, storing tapes in S3 and archiving to Glacier for long-term retention and compliance.

---
**Q3:** A media company wants to provide its editors with fast, local access to large video files while ensuring all files are backed up to S3. Which Storage Gateway solution is best?
- A) File Gateway
- B) Volume Gateway
- C) Tape Gateway
- D) Snowball Edge

**Answer:** A. File Gateway provides NFS/SMB file shares with local cache and backs up files to S3.

---
**Q4:** What is a key consideration when sizing the local cache disk for a File Gateway?
- A) It determines the maximum file size
- B) It impacts the performance and frequency of cloud access
- C) It limits the number of file shares
- D) It is only used for Tape Gateway

**Answer:** B. Cache size impacts performance; too small a cache leads to frequent cloud access and slower performance.

---
**Q5:** Which Storage Gateway type allows you to ingest on-premises data into S3 for analytics with Athena or Redshift?
- A) File Gateway
- B) Volume Gateway
- C) Tape Gateway
- D) Direct Connect

**Answer:** A. File Gateway stores files as objects in S3, enabling analytics with Athena, Redshift, or EMR.
