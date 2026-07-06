# Data Specification

## Overview

This document defines the business rules, data structure, and validation requirements adopted by the **Cultural Program Impact Dashboard**.

Its purpose is to ensure consistency throughout data collection, transformation, modeling, and visualization.

---

# Business Rules

## BR-001

Each municipality may submit only one evaluation for each program edition.

---

## BR-002

Each survey response represents a single municipality.

---

## BR-003

The Municipality field is mandatory.

---

## BR-004

The Responsible Public Agency field is mandatory.

---

## BR-005

All quantitative evaluation questions are mandatory.

---

## BR-006

The Suggestions field is optional.

---

## BR-007

Evaluation scores must range from **1** to **5**.

| Score | Meaning |
|------:|---------|
| 1 | Very Poor |
| 2 | Poor |
| 3 | Fair |
| 4 | Good |
| 5 | Excellent |

---

## BR-008

The Continuity question accepts only the following values:

- Yes
- No
- Not sure

---

## BR-009

Only completed questionnaires are considered in the dashboard indicators.

---

## BR-010

Qualitative responses are used only for descriptive analysis and are not included in numerical calculations.

---

# Survey Fields

| Field | Type | Required |
|--------|------|:--------:|
| Municipality | Short Text | Yes |
| Public Agency | Dropdown | Yes |
| Relevance | Integer | Yes |
| Efficiency | Integer | Yes |
| Effectiveness | Integer | Yes |
| Impact | Integer | Yes |
| Reach | Integer | Yes |
| Continuity | Single Choice | Yes |
| Overall Satisfaction | Integer | Yes |
| Suggestions | Long Text | No |

---

# Data Dictionary

| Field | Data Type | Description |
|--------|-----------|-------------|
| Municipality | Text | Municipality participating in the program |
| PublicAgency | Text | Municipal public agency responsible for the program |
| Relevance | Integer | Relevance evaluation score (1–5) |
| Efficiency | Integer | Efficiency evaluation score (1–5) |
| Effectiveness | Integer | Effectiveness evaluation score (1–5) |
| Impact | Integer | Perceived impact evaluation score (1–5) |
| Reach | Integer | Reach evaluation score (1–5) |
| Continuity | Text | Future participation interest (Yes, No, Not sure) |
| OverallSatisfaction | Integer | Overall satisfaction score (1–5) |
| Suggestions | Text | Optional qualitative feedback |

---

# Validation Rules

- Municipality cannot be empty.
- Public Agency cannot be empty.
- Quantitative scores must be integers between **1** and **5**.
- Continuity accepts only **Yes**, **No**, or **Not sure**.
- Suggestions are optional.
- Each questionnaire represents one municipality.

---

# Expected Output

The collected data will support the calculation of indicators such as:

- Average Relevance Score
- Average Efficiency Score
- Average Effectiveness Score
- Average Impact Score
- Average Reach Score
- Overall Satisfaction Score
- Interest in Future Participation
- Qualitative Suggestions Summary
