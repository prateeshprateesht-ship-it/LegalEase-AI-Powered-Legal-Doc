# LegalEase: AI-Powered Legal Document Generator

A BCA final-year project prototype built with **Python standard library, SQLite, HTML/CSS and ReportLab**. LegalEase converts structured user input into readable first-draft legal documents, stores them in a local database, and exports them as PDF files.

> **Important:** This is an educational software project. Generated documents are drafts and should be reviewed by a qualified legal professional before real-world use.

## 1. Main Features

- Clean responsive dashboard
- Legal document generator
- Four document templates:
  - Rental Agreement
  - Employment Contract
  - Non-Disclosure Agreement
  - Affidavit
- Dynamic input forms
- Automatic document generation
- SQLite persistence for generated documents
- Document preview page
- One-click PDF download
- JSON API endpoint at `/api/generate`
- Fallback drafting engine so the demo works without a paid AI API

## 2. Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML5, CSS3, Jinja2 |
| Backend | Python 3 standard library HTTP server |
| Database | SQLite + SQLAlchemy |
| PDF | ReportLab |
| Architecture | Lightweight layered Python web application |

## 3. Folder Structure

```text
LegalEase/
├── app.py
├── requirements.txt
├── .env.example
├── README.md
├── templates/
│   ├── base.html
│   ├── index.html
│   ├── generate.html
│   └── document.html
├── static/
│   └── style.css
└── instance/
```

The SQLite database is created automatically on first run.

## 4. Installation

### Windows

1. Install Python 3.10 or newer.
2. Open Command Prompt in the project directory.
3. Create a virtual environment:

```bash
python -m venv venv
```

4. Activate it:

```bash
venv\\Scripts\\activate
```

5. Install dependencies:

```bash
pip install -r requirements.txt
```

6. Start the application:

```bash
python app.py
```

7. Open:

```text
http://127.0.0.1:5000
```

### macOS / Linux

```bash
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
python app.py
```

Then open `http://127.0.0.1:5000`.

## 5. How to Demonstrate the Project

1. Open the dashboard.
2. Select **Generate Document**.
3. Select **Rental Agreement**.
4. Enter sample details.
5. Click **Generate with LegalEase AI**.
6. Review the generated document.
7. Click **Download PDF**.
8. Repeat with Employment Contract, NDA, and Affidavit.

### Suggested demo data

- Client: Priya Sharma
- Other party: Arun Kumar
- Jurisdiction: Chennai, Tamil Nadu, India
- Property: 21 Anna Nagar, Chennai
- Start date: 01-10-2026
- End date: 30-09-2027
- Monthly rent: INR 18,000

## 6. Project Modules

### User Interface Module
Provides the dashboard, document form, document preview and navigation.

### Document Generation Module
`generate_document()` receives structured form data and creates a document draft using the selected legal template.

### Database Module
The `LegalDocument` model stores document type, client name, jurisdiction, content and creation time in SQLite.

### PDF Module
ReportLab converts the generated document into a downloadable PDF.

### API Module
`POST `/api/generate`` accepts JSON and returns generated document content, allowing a future mobile app or React frontend to consume the backend.

## 7. AI Extension

The current version uses a deterministic drafting engine so the project is reliable for a college demonstration and does not require an API key. For a production-style extension, replace the `generate_document()` implementation with an LLM provider and retain the same form/database/PDF architecture.

A suitable future pipeline is:

```text
User Form
   ↓
Input Validation
   ↓
Prompt Builder
   ↓
LLM / Local Model
   ↓
Legal Draft Validator
   ↓
Document Preview
   ↓
PDF Export
```

## 8. Database Schema

### LegalDocument

- `id` – primary key
- `title` – document title
- `document_type` – selected legal document type
- `client_name` – primary user/client
- `jurisdiction` – applicable jurisdiction
- `content` – generated document text
- `created_at` – creation timestamp

## 9. Future Enhancements

- User authentication and role-based access
- More legal templates
- LLM-based personalized drafting
- Clause recommendation engine
- Multi-language support
- Digital signatures
- Document versioning
- Search and filtering
- Cloud storage
- Lawyer review workflow
- Audit logs

## 10. Academic Project Objectives

1. Reduce the time required to prepare common legal-document drafts.
2. Provide a simple form-driven legal drafting interface.
3. Demonstrate AI-assisted document generation concepts.
4. Store and retrieve generated documents using a relational database.
5. Provide downloadable professional-looking PDF output.

## 11. Limitations

- The included generator is a project prototype, not a legal-advice system.
- Templates do not cover every jurisdiction-specific requirement.
- No authentication is included in the starter version.
- Human legal review is required for real-world documents.

## 12. License

This project is intended for educational and academic demonstration purposes.
