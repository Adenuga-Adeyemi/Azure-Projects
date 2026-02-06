Azure-based data & integration platform for **SafeSure Insurance Nigeria**

## Overview

**SafeSure Insurance Nigeria** provides auto, health, property, and life assurance products across major cities including **Lagos**, **Abuja**, **Port-Harcourt**, **Kano**, and **Enugu**.

**Vision**: Make insurance more accessible and transparent for every Nigerian through digital channels.

**Current challenges**:

- **Sales & Product team** → Product catalog and pricing stored in **CSV files** (versioned in GitHub)
- **Operations team** → Daily transactions, premiums, claims, and policy data managed in an **on-premises SQL Server** database
- **Customer experience & incident team** → Customer-submitted incident reports, photos, documents, and supporting files uploaded to **Azure Data Lake Storage Gen2** but with inconsistent formats, naming conventions, date styles (DD-MM-YY vs YYYY-MM-DD vs others), missing metadata, and variable quality

This project ("safesure-cluster") aims to build a modern, cloud-native **data & integration backbone** on **Azure** that:

- Unifies data from CSV, SQL, and ADLS Gen2 sources
- Enables consistent ingestion, cleaning, standardization, and enrichment
- Powers digital channels, analytics, reporting, fraud detection, claims automation, and customer-facing portals
- Supports future AI/ML use cases (e.g. document understanding, risk scoring, chatbots)

## Goals

- Create a single source of truth for product, policy, claims, and incident data
- Standardize incident report formats and metadata in ADLS Gen2
- Enable near real-time and batch analytics
- Reduce manual reconciliation effort across departments
- Provide secure, governed access for Power BI, APIs, and future mobile/web apps

## Architecture (high-level)

```text
CSV files (GitHub) ──► Azure Data Factory / Synapse Pipelines ──► Bronze ──► Silver ──► Gold
On-prem SQL ────────┘                                 (ADLS Gen2 layers)
Incident uploads ───┘
                                                        ↓
                                            Azure Synapse Analytics / Databricks
                                                        ↓
                                            Power BI • Customer portal


