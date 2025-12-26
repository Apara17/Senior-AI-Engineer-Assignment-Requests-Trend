# Senior AI Engineer Assignment

## Overview
This repository contains my submission for the **Senior AI Engineer Assignment** by Pulsegen Technologies.

The project focuses on extracting and analyzing **user requests and feature suggestions** from Google Play Store reviews. Reviews are processed as **daily batches**, and an agentic AI pipeline is used to identify, normalize, and track evolving user demands over a 30-day rolling window.

The entire solution is implemented and demonstrated using **Google Colab**.

---

## Problem Statement
- Source: Google Play Store reviews (Swiggy app)
- Data Handling: Daily batches
- Objective:
  - Identify user **requests and feature suggestions**
  - Consolidate semantically similar requests
  - Generate a 30-day trend analysis (T to T-30)

### Output Format
- Rows: Request topics
- Columns: Dates (T to T-30)
- Cells: Frequency of request occurrence on that date

---

## Solution Approach (Agentic Design)

### Agent 1: Intent Classifier
- Processes daily reviews
- Identifies reviews expressing **user intent or requests**
- Filters out generic feedback or unrelated content

### Agent 2: Request Normalizer
- Uses sentence embeddings and cosine similarity
- Merges semantically similar requests into a single canonical request
- Prevents fragmented request categories

### Agent 3: Trend Analyzer
- Tracks normalized requests day-by-day
- Builds a rolling 30-day trend table
- Assigns zero counts for days with no data

---

## Handling Sparse Data
In the observed review window, data was available only for a limited number of days.  
The system:
- Correctly handles missing days
- Does not fabricate trends
- Maintains a complete T to T-30 window as required

This reflects real-world product feedback systems where user activity may be uneven.

---

