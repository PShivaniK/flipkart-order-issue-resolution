# Flipkart Order Issue Resolution & Customer Support Analytics

## 📋 Project Overview
This project focuses on analyzing e-commerce operational data, customer complaints, delivery delays, and refund lifecycles for Flipkart orders. The goal is to uncover root causes for delivery bottlenecks, track support ticket resolution efficiency, and establish a priority classification framework to resolve high-risk customer issues proactively.

---

## 📂 Dataset Files Used
The analysis integrates multiple operational datasets:
* **`orders.csv`**: Main order lifecycle transactions, order amounts, timestamps, statuses, and delivery cities.
* **`customers.csv`**: Customer demographic and profile details.
* **`sellers.csv`**: Seller categories and metadata.
* **`support_tickets.csv`**: Support ticket escalation flags, assigned teams, and resolution times in hours.
* **`refunds.xlsx`**: Refund tracking, amounts, statuses, and processing channels.
* **`customer_complaints.json`**: Customer-reported issues, categories, sentiment tags, and complaint statuses.
* **`status_notes.txt`**: Additional qualitative logs and status context.

---

## ⚙️ Key Technical Workflow & Steps
1. **Data Ingestion & Cleaning**: 
   * Loaded CSV, Excel, JSON, and text logs into pandas.
   * Standardized string categories (`.str.strip().str.title()`) to prevent duplicate groupings caused by casing or whitespace inconsistencies.
   * Converted date-time columns to proper datetime objects for duration and SLA calculations.
2. **Data Validation & Integrity Checks**:
   * Scanned for duplicate primary keys across all tables.
   * Identified and audited foreign key relationships to catch orphaned child records (e.g., support tickets or refunds referencing non-existent order IDs).
3. **Master Table Merging**:
   * Performed controlled `left` joins to aggregate orders with customer metadata, seller categories, support tickets, refunds, and complaints without causing accidental row explosions.
4. **Exploratory Data Analysis & Visualizations**:
   * Analyzed order status distributions (Delivered, Delayed, Cancelled).
   * Evaluated top cities experiencing the highest delivery delays.
   * Quantified customer complaint categories and repeat-complaint orders.
5. **Priority Classification**:
   * Combined multiple business signals (such as escalated support tickets and pending/failed refund requests) to isolate high-priority operational bottlenecks.

---

## 🚀 How to Run the Notebook
1. Open the `.ipynb` notebook file inside **Google Colab**.
2. Mount your Google Drive or upload the required dataset files to your Colab environment matching your folder path setup.
3. Run all code cells sequentially from top to bottom to replicate data preprocessing, validations, visualizations, and summary reports.

---

## 📌 Deliverable Link
* **Google Colab Notebook**: [Insert Public Colab View Link Here]
