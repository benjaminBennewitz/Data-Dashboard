<p align="center">
  <img src="./assets/readme/hero.svg" alt="Daten Dashboards — Local Lab Insight Hub" width="100%" />
</p>

<p align="center">
  <a href="#status"><img alt="Status" src="https://img.shields.io/badge/status-early%20development-00478D?style=for-the-badge" /></a>
  <a href="#tech-stack"><img alt="Angular" src="https://img.shields.io/badge/frontend-Angular-005EB8?style=for-the-badge" /></a>
  <a href="#tech-stack"><img alt="Django REST Framework" src="https://img.shields.io/badge/backend-Django%20REST-00478D?style=for-the-badge" /></a>
  <a href="#local-first"><img alt="Local first" src="https://img.shields.io/badge/processing-local%20first-2E7D55?style=for-the-badge" /></a>
  <a href="#medical-disclaimer"><img alt="No diagnosis" src="https://img.shields.io/badge/medical-no%20diagnosis-BA1A1A?style=for-the-badge" /></a>
</p>

---

## Overview

**Daten Dashboards** is a local lab-results assistant for structured PDF analysis, medical review, and clear patient reports.

The project is designed as a complete workflow from uploaded test lab reports to reviewed values, dashboard-based analysis, and understandable patient-facing summaries. It does **not** provide diagnoses. Medical assessment and final approval always remain with the doctor.

---

## Core Idea

> Turn complex lab reports into structured, comparable, doctor-reviewed and patient-friendly information.

The system focuses on:

| Area | Purpose |
| --- | --- |
| **Import** | Upload optimized test PDFs or manually start a prepared demo analysis. |
| **Extraction** | Read PDF text layers or use local OCR for image-based reports. |
| **Normalization** | Detect lab values, units, reference ranges and comparable parameter keys. |
| **Review** | Let doctors verify uncertain values with original snippets side by side. |
| **Dashboard** | Analyze trends, abnormal values, confidence scores and report comparisons. |
| **Patient Report** | Generate a clear, print-ready explanation based only on approved data. |

---

## Workflow

<p align="center">
  <img src="./assets/readme/workflow.svg" alt="Daten Dashboards workflow" width="100%" />
</p>

---

## Feature Highlights

### Doctor Workspace

- Test-data PDF download directly from the start screen
- Demo analysis with prepared artificial data
- Local PDF text extraction
- Local OCR fallback for image-based lab reports
- Import status with progress and confidence information
- Review queue for uncertain or abnormal values
- Side-by-side comparison of original snippet and extracted value
- Correction form for result, unit and reference range
- Doctor approval before report generation

### Data Analysis

- Lab value grouping by medical area
- Abnormal value prioritization
- Confidence score per extracted value
- Trend charts across multiple reports
- Report comparison views
- Value distribution by traffic-light status
- Dashboard cards for quick clinical overview

### Patient Report

- Responsive HTML report
- Print-optimized layout
- Patient-friendly explanations from controlled knowledge content
- Clear distinction between normal, high and low values
- Suggested questions for the doctor conversation
- Mandatory disclaimer that the report does not replace a diagnosis

### Knowledge Base

- Controlled explanation texts instead of runtime-generated medical advice
- JSON seed support for initial content
- Editable entries for doctors or admins
- Versioned text content
- Source fields and status flags
- Separate patient explanation and doctor information fields

---

## Tech Stack

| Layer | Technology |
| --- | --- |
| **Frontend** | Angular |
| **Backend** | Django + Django REST Framework |
| **Database** | PostgreSQL |
| **Jobs** | Celery |
| **Queue / Broker** | Redis |
| **File Storage** | Private local media storage through the own API |
| **PDF Processing** | Local PDF text analysis |
| **OCR** | Local OCR pipeline, for example Tesseract |
| **Reports** | Responsive HTML + print CSS, optional local PDF export later |

---

## Local First

Daten Dashboards is planned as a local-first analysis system:

- No external OCR services
- No external medical analysis APIs
- No cloud-based patient data processing
- Files remain in local storage
- Analysis results stay in the own API and database
- The demo workflow uses only artificial, anonymized test data

---

## Data Model Goals

The database model is planned to support at least **3NF** and, where useful, **BCNF**.

Key domains:

- Test persons
- Lab reports
- Lab values
- Reference ranges
- Import jobs
- Extraction results
- Review status
- Knowledge base entries
- Text versions
- Patient reports
- Audit and approval states

---

## Design Direction

The interface follows a soft **neomorphic clinical dashboard** style:

| Token | Value |
| --- | --- |
| Background | `#F9F9FF` |
| Surface | `#F2F3FB` |
| Raised shadow | `-8px -8px 16px #FFFFFF`, `8px 8px 16px #D1D9E6` |
| Primary | `#00478D` |
| Primary container | `#005EB8` |
| Text | `#191C21` |
| Muted text | `#424752` |
| Success | `#2E7D55` |
| Warning | `#C77700` |
| Error | `#BA1A1A` |

The UI should feel precise, calm and data-focused. Graphs, value trends, confidence indicators and comparison views are visually prioritized over decorative elements.

---

## Planned App Areas

```text
Start Screen
├── Test-data PDF download
├── Demo analysis
└── Upload entry point

Import & Analysis
├── Upload jobs
├── PDF extraction
├── OCR fallback
├── Confidence scoring
└── Pipeline status

Medical Review
├── Uncertain values
├── Original snippet
├── Extracted value
├── Correction form
└── Approval workflow

Analysis Dashboard
├── Value groups
├── Trend charts
├── Abnormal values
├── Report comparison
└── Patient report generation

Knowledge Base
├── Lab value explanations
├── Patient text
├── Doctor notes
├── Sources
└── Version history

Patient Report
├── Summary
├── Abnormal values
├── Explanations
├── Questions for doctor visit
└── Disclaimer
```

---

## Status

This repository is in early project setup. The current focus is on:

- Base architecture
- Design system
- Data model planning
- Import workflow structure
- Local PDF and OCR processing concept
- Dashboard and review UX

---

## Medical Disclaimer

This project is built for structured lab-data processing and understandable report preparation. It does **not** provide medical diagnoses, treatment decisions or automated medical approval. All medical interpretation and final release must be performed by a qualified doctor.

---

## License

License information will be added later.
