# T4: HubSpot to Self-Hosted Twenty Migration

This repository contains the migration files and exports for migrating a HubSpot CRM to a self-hosted Twenty instance on Selfhost.dev.

## Final Report
The full write-up and migration report is available in the [Migration Report Google Doc](https://docs.google.com/document/d/1Oc7FDF4N-y3BEDVrOUEFjaflwKLbGXp8fsz-4c7FYMU/edit?usp=sharing).

## Contents
* **companies.csv**: HubSpot export of 100 companies.
* **contacts.csv**: HubSpot export of 300 contacts.
* **deals.csv**: HubSpot export of 40 deals.
* **contacts_with_domains.csv**: A 10-row test file used to test Twenty's contact-company linking importer.

## Key Findings
* **Data Migrated:** 100 Companies, 300 Contacts, 40 Deals.
* **Duplicate Test:** Re-importing Companies blocked 99 duplicates (105 to 106). Re-importing Contacts did **not** block duplicates (300 to 605), which were then manually deleted.
* **HubSpot Limitations:** HubSpot Free blocks Workflows completely and prevents reliable bulk export of Notes/Tasks.
* **Link Test:** Twenty's CSV importer failed to auto-associate People to Companies, even when the correct domain was mapped. Manual linking is required.

## Migration Runbook
1. Deployed Twenty on Selfhost.dev (4 vCPU, 8 GB RAM).
2. Created custom fields (Lead Source, Plan Interest) and 5 pipeline stages.
3. Imported Companies, Contacts, and Deals via CSV.
4. Rebuilt workflows manually. Could not rebuild forms (Twenty limitation).
5. Invited second user via invite link.

## Field Mapping Table
| HubSpot Field | Twenty Field |
| :--- | :--- |
| Company Name | Name |
| Domain | Domain Name |
| Lead Source | Lead Source (Custom) |
| First Name | Name / First Name |
| Last Name | Name / Last Name |
| Email | Emails / Primary Email |
| Plan Interest | Plan Interest (Custom) |
| Deal Name | Name |
| Amount | Amount |
| Deal Stage | Stage |
| Pipeline | Pipeline |
