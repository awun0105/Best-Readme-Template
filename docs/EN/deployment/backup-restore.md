<!-- 
BACKUP AND RESTORE TEMPLATE
===========================
Focus: State preservation and recovery procedures.

AGENT EXECUTION PROTOCOL:
1. Identify database dump commands and object store backup logic.
2. Resolve [brackets].
3. Clean up instructional notes.
-->

# Backup and Restore

Procedures for state preservation and disaster recovery for **[Project Title / Name]**.

## Backup Strategy

- **Database**: [e.g., pg_dump daily].
- **Object Storage**: [e.g., rclone sync to S3].
- **Configuration**: [e.g., Encrypted secret vault].

## Recovery Check (Restoring)

### 1. Database Restore
```bash
# Example command
psql -U [user] [db_name] < backup.sql
```

### 2. Object Storage Restore
*Instructions for restoring binaries/files.*

## Automated Checks
*Explain any scripts or cron jobs that verify backup integrity.*

---

<div align="center">

[Back to Documentation Index](../README.md)

</div>
