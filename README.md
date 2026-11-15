# T4: HubSpot to Self-Hosted Twenty Migration

This repository contains the migration files, exports, and final report for migrating a HubSpot CRM to a self-hosted Twenty instance on Selfhost.dev.

## Contents
* **T4_HubSpot_to_Twenty_Report_Himanshu.pdf**: The final report containing the migration map, duplicate handling tests, and platform limitations.
* **companies.csv**: HubSpot export of 100 companies.
* **contacts.csv**: HubSpot export of 300 contacts.
* **deals.csv**: HubSpot export of 40 deals.

## Key Findings
* **Data Migrated:** 100 Companies, 300 Contacts, 40 Deals.
* **Duplicate Test:** Twenty successfully blocked 99 duplicate records during a re-import test.
* **HubSpot Limitations:** HubSpot Free blocks Workflows completely and prevents reliable bulk export of Notes/Tasks.
* **Link Test:** Imported contacts do not automatically link to companies in Twenty (manual linking required).
