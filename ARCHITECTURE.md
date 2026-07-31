# Architecture Overview

Product Data Studio Pro is a Windows desktop application for preparing
e-commerce product catalogs.

> This document describes the product at a high level. The application is
> proprietary, and the complete internal source architecture is maintained in a
> private repository.

## High-level architecture

```text
Windows Desktop Interface
    ↓
Catalog Workflow Services
    ↓
Validation and Transformation Engine
    ↓
Local Catalog Data
    ↓
Excel / CSV / JSON / ZIP output
```

## Main components

### Desktop interface

The interface provides:

- Excel and CSV import;
- column mapping;
- catalog preview;
- issue review;
- guided fixes;
- batch workflows;
- English and Russian language selection;
- export tools.

### Catalog workflow services

Workflow services coordinate:

- cleaning;
- validation;
- comparison;
- merging;
- splitting;
- combining;
- transformation recipes;
- batch processing;
- marketplace publishing.

### Validation engine

The validation engine performs:

- structural checks;
- duplicate SKU detection;
- price and category checks;
- image URL checks;
- smart detection of suspicious values;
- user-defined validation rules.

### Transformation engine

Transformation recipes support reusable operations such as:

- whitespace normalization;
- text case conversion;
- prefix and suffix creation;
- find and replace;
- numeric calculations;
- rounding;
- copying and combining columns.

### Marketplace exporters

The application creates customer-reviewable files for:

- Shopify;
- WooCommerce.

Products with blocking issues can be excluded into separate review reports.

## Local-first processing

Product Data Studio Pro uses a local-first design:

```text
Catalog file
    ↓
Processing on the user’s Windows computer
    ↓
User-selected output folder
```

The application does not require catalog files to be uploaded to an external
service.

## Windows distribution

The commercial version is distributed as:

```text
Product_Data_Studio_Pro_2.2.0.zip
└── ProductDataStudioPro_Setup.exe
```

The Windows application is packaged using PyInstaller and installed using Inno
Setup. Customers do not need Python or PyCharm.

## Technology

- Python
- PySide6
- pandas
- openpyxl
- PyInstaller
- Inno Setup

## Repository separation

### Private repository

Contains:

- full source code;
- tests;
- build scripts;
- installer configuration;
- internal release materials.

### Public showcase repository

Contains only:

- product overview;
- feature documentation;
- architecture overview;
- screenshots;
- privacy information;
- system requirements;
- Gumroad link.

The public showcase does not contain source code or paid distribution files.
