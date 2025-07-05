# dbt BigQuery Setup Guide

This README documents the full setup process for a dbt project using **Google BigQuery** as the data warehouse. It includes all commands used, along with explanations.

---

## 📦 Prerequisites

- Python 3.7+
- `pip` (Python package manager)
- `gcloud` CLI configured with your GCP account
- BigQuery dataset and project already created

---

## 🧰 Step-by-Step Setup with Commands

### 1. ✅ Create a Virtual Environment

```bash
python3 -m venv dbtProjects


source dbtProjects/bin/activate
Purpose: Enables the virtual environment so all pip packages are installed locally.

pip install dbt-core dbt-bigquery

Purpose: Installs the dbt CLI and the plugin needed to connect to BigQuery

dbt --version
Purpose: Verifies that dbt is installed and shows which adapters are available.

dbt init dbtproject
Purpose: Creates a new folder (dbtproject/) with the dbt project structure and optionally sets up your BigQuery connection.

⚠️ If you hit Ctrl+C, you might need to manually set up ~/.dbt/profiles.yml

cd dbtproject
Moves into the generated dbt project folder

dbt debug
Validates installation, profiles.yml, and confirms connectivity to BigQuery.

dbt run           # Run all models
dbt test          # Run tests defined in schema.yml
dbt compile       # Compile SQL without running
dbt docs generate # Generate documentation site
dbt docs serve    # Launch local documentation viewer

Setting Up profiles.yml
The profiles.yml file is how dbt knows how to connect to your data warehouse — in this case, Google BigQuery.

✅ Where Should It Be Located?
It must be located in the following path on your system:

bash
Copy
Edit
~/.dbt/profiles.yml
That translates to:

On Linux/Mac: /home/<your-username>/.dbt/profiles.yml

On Windows (PowerShell): C:\Users\<your-username>\.dbt\profiles.yml

📝 This file is user-specific and lives outside your dbt project folder.
