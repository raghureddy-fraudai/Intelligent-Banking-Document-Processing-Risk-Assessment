# BankDocAI - Enterprise Banking Document Intelligence Platform

## Overview

BankDocAI is an AI-powered banking document processing platform that automates OCR extraction, transaction intelligence, risk assessment, sentiment analysis, and compliance validation from bank statements.

## Features

* OCR-based PDF and image processing
* Automated customer and transaction extraction
* Pydantic-powered data validation
* Transaction categorization engine
* Sentiment analysis module
* Risk scoring and anomaly detection
* Audit logging and workflow tracking
* FastAPI REST API deployment
* Real-time document intelligence pipeline

## Technology Stack

* Python
* FastAPI
* Pydantic
* Tesseract OCR
* PDF2Image
* Pandas
* Uvicorn
* Regular Expressions
* REST APIs

## System Workflow

1. Document Upload
2. OCR Text Extraction
3. Entity & Transaction Parsing
4. Data Validation
5. Transaction Categorization
6. Sentiment Analysis
7. Risk Detection
8. Risk Scoring
9. Audit Logging
10. API Response Generation

## Architecture Diagram

```mermaid
flowchart TD

A[Bank Statement PDF/Image]
--> B[OCR Engine - Tesseract OCR]

B --> C[Entity Extraction Layer]
B --> D[Transaction Extraction Layer]

C --> E[Pydantic Validation]
D --> E

E --> F[Transaction Categorization]

F --> G[Sentiment Analysis]

G --> H[Risk Detection Engine]

H --> I[Risk Scoring & Executive Summary]

I --> J[Audit Logging]

J --> K[FastAPI REST API]

K --> L[JSON Response]
```

## Sample Output

### Workflow Progress & API Response

The following demonstrates the complete document processing pipeline with workflow stages and the generated risk assessment JSON response:

```
[Workflow Progress] Stage: DOCUMENT_RECEIVED, Status: SUCCESS, Details: /content/BANK_STATEMENT_2.pdf
Successfully extracted text from /content/BANK_STATEMENT_2.pdf.
[Workflow Progress] Stage: AI_UNDERSTANDING, Status: SUCCESS, Details:
[Workflow Progress] Stage: VALIDATION, Status: SUCCESS, Details: Schema validation passed
[Workflow Progress] Stage: SUMMARY_GENERATION, Status: SUCCESS, Details: REVIEW_RECOMMENDED
INFO:     127.0.0.1:49288 - "POST /process-document HTTP/1.1" 200 OK

--- DOWNSTREAM SERVER INGESTION RESULTS ---
{
  "status": "SUCCESS",
  "risk_summary": {
    "customer_name": "CH JANAKI RAGHU RAMI REDDY MADHAVANAGAR KURNOOL",
    "bank_name": "World Bank of Baroda",
    "total_transactions": 24,
    "high_risk_flags": 1,
    "medium_risk_flags": 0,
    "risk_score": 65,
    "recommended_action": "REVIEW_RECOMMENDED",
    "executive_summary": "CH JANAKI RAGHU RAMI REDDY MADHAVANAGAR KURNOOL has 24 items. System tracked 1 high-risk anomalies. Action: REVIEW_RECOMMENDED."
  },
  "risk_flags_count": 1,
  "audit_log_count": 4
}
```

### Direct Workflow Execution

![Direct Workflow Execution](https://raw.githubusercontent.com/raghureddy-fraudai/Intelligent-Banking-Document-Processing-Risk-Assessment/refs/heads/main/assets/Screenshot%202026-06-10%20111547.png)

### Categorized Transactions (Refined Rules)

Transaction categorization using refined rule-based engine with intelligent classification of all extracted transactions:

![Categorized Transactions](https://raw.githubusercontent.com/raghureddy-fraudai/Intelligent-Banking-Document-Processing-Risk-Assessment/refs/heads/main/assets/Screenshot%202026-06-10%20111601.png)

### Transactions with Sentiment Analysis

Comprehensive transaction analysis with sentiment classification for each transaction extracted from the bank statement:

![Transactions with Sentiment Analysis](https://raw.githubusercontent.com/raghureddy-fraudai/Intelligent-Banking-Document-Processing-Risk-Assessment/refs/heads/main/assets/Screenshot%202026-06-10%20Sentiment%20Analysis.png)

### OCR Extraction & Transaction Intelligence

Processing bank statement using the real OCR engine and successfully extracting text from PDF documents:

```
Processing bank statement using the real OCR engine...
Successfully extracted text from /content/BANK_STATEMENT_2.pdf.

--- Extracted Header Entities ---
account_number: 81198100000007
ifsc: BARB0VJMDNG
bank_name: World Bank of Baroda
customer_name: CH JANAKI RAGHU RAMI REDDY MADHAVANAGAR KURNOOL
pan: None
mobile: None
email: None
statement_period: 01-12-2024 to 31-01-2025

--- Extracted Transactions ---
Transaction 1: {'date': '03-12-2024', 'description': 'Opening Balance', 'transaction_type': 'UNKNOWN', 'amount': 0.0, 'balance': 8.35}
Transaction 2: {'date': '05-12-2024', 'description': 'JPN A TOSOTOSTSSIA ASS D/EHSSOTSHEB8S 1DP4', 'transaction_type': 'CREDIT', 'amount': 1200.0, 'balance': 1200.35}
Transaction 3: {'date': '05-12-2024', 'description': 'UR SERA UA SERIA', 'transaction_type': 'DEBIT', 'amount': 150.0, 'balance': 950.35}
Transaction 4: {'date': '10-12-2024', 'description': '(Puat1181281.44/19*30:05/1Pubharatpe. 200093587', 'transaction_type': 'DEBIT', 'amount': 10.0, 'balance': 19.92}
Transaction 5: {'date': '08-01-2025', 'description': 'AS LE AEDT', 'transaction_type': 'DEBIT', 'amount': 19.0, 'balance': 0.29}
```

## Business Applications

* Banking Automation
* Financial Document Intelligence
* KYC Verification
* Fraud Detection Support
* Compliance Monitoring
* Risk Assessment

## Future Enhancements

* LLM-powered Document Understanding
* RAG-based Financial Assistant
* Multi-bank Support
* Machine Learning Fraud Detection
* Dashboard & Analytics Portal
* Cloud Deployment using Docker & Kubernetes
