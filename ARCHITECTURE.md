# Architecture Overview

Product Data Studio Pro is a Windows desktop application for preparing
e-commerce product catalogs.

> This document contains a high-level public architecture only. The complete
> implementation remains in a private repository.

## High-level architecture

```mermaid
flowchart TD
    UI[Windows Desktop Interface]
    SERVICES[Catalog Workflow Services]
    ENGINE[Validation and Transformation Engine]
    DATA[Local Catalog Data]
    OUTPUT[Excel / CSV / JSON / ZIP Output]

    UI --> SERVICES
    SERVICES --> ENGINE
    ENGINE --> DATA
    DATA --> OUTPUT
```

## Main product components

```mermaid
flowchart LR
    APP[Product Data Studio Pro]

    APP --> IMPORT[Excel / CSV Import]
    APP --> VALIDATE[Catalog Validation]
    APP --> TRANSFORM[Transformation Recipes]
    APP --> COMPARE[Catalog Comparison]
    APP --> MERGE[Supplier Update Merge]
    APP --> BATCH[Batch Workflows]
    APP --> MARKET[Marketplace Export]
    APP --> LANG[English / Russian Interface]
```

## Catalog workflow

```mermaid
flowchart TD
    FILE[Excel or CSV Catalog]
    MAP[Column Mapping]
    CLEAN[Cleaning]
    VALIDATE[Validation]
    FIX[Guided Fixes]
    EXPORT[Marketplace Export]

    FILE --> MAP
    MAP --> CLEAN
    CLEAN --> VALIDATE
    VALIDATE --> FIX
    FIX --> EXPORT
```

## Validation model

```mermaid
flowchart LR
    ENGINE[Validation Engine]
    STANDARD[Standard Checks]
    SMART[Smart Validation]
    CUSTOM[Custom Rules]

    ENGINE --> STANDARD
    ENGINE --> SMART
    ENGINE --> CUSTOM
```

The application can detect missing product data, duplicate SKUs, invalid prices,
invalid image URLs, suspicious values, and values copied into the wrong columns.

## Batch processing

```mermaid
flowchart LR
    FILES[Multiple Catalogs]
    AUDIT[Batch Audit]
    REPAIR[Batch Repair]
    REVIEW[Manual Review]
    PUBLISH[Batch Publish]

    FILES --> AUDIT
    AUDIT --> REPAIR
    REPAIR --> REVIEW
    REVIEW --> PUBLISH
```

## Local-first processing

```mermaid
flowchart TD
    INPUT[Catalog File]
    LOCAL[Local Windows Processing]
    OUTPUT[User-selected Output Folder]

    INPUT --> LOCAL
    LOCAL --> OUTPUT
```

Catalog files are processed on the user's Windows computer. The application does
not require catalog data to be uploaded to an external service.

## Windows distribution

```mermaid
flowchart LR
    ZIP[Customer ZIP]
    SETUP[ProductDataStudioPro_Setup.exe]
    INSTALL[Windows Installation]
    APP[Product Data Studio Pro]

    ZIP --> SETUP
    SETUP --> INSTALL
    INSTALL --> APP
```

Customers do not need Python or PyCharm.

## Technology

- Python
- PySide6
- pandas
- openpyxl
- PyInstaller
- Inno Setup

## Repository separation

```mermaid
flowchart TD
    PRODUCT[Product Data Studio Pro]

    PRODUCT --> PRIVATE[Private Repository]
    PRODUCT --> PUBLIC[Public Showcase]

    PRIVATE --> P1[Full Source Code]
    PRIVATE --> P2[Tests and Build Scripts]
    PRIVATE --> P3[Installer Configuration]

    PUBLIC --> U1[README and Documentation]
    PUBLIC --> U2[Screenshots]
    PUBLIC --> U3[Privacy and System Requirements]
    PUBLIC --> U4[Gumroad Link]
```

The public showcase does not contain source code, EXE files, or paid customer
downloads.
