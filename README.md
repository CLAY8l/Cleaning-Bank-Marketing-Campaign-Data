# Cleaning Bank Marketing Campaign Data

![Piggy bank](piggy_bank.jpg)

This project cleans and reorganizes a bank marketing campaign dataset. The original dataset contains customer information, campaign contact details, campaign outcomes, and economic indicators related to a personal-loan marketing campaign.

The data-cleaning workflow is implemented in [`notebook.ipynb`](notebook.ipynb) using Python, pandas, and NumPy.

## Project goals

The notebook prepares the raw campaign data for analysis by:

- Cleaning inconsistent categorical values, including replacing periods with underscores where appropriate.
- Converting unknown education values to missing values.
- Converting selected categorical fields to Boolean values.
- Creating a `last_contact_date` field from the contact day, month, and campaign year (`2022`).
- Splitting the cleaned dataset into client, campaign, and economic data subsets.
- Exporting the cleaned subsets as CSV files.

## Repository structure

```text
.
├── data/
│   ├── bank_marketing.csv   # Original dataset
│   ├── campaign.csv         # Campaign contact and outcome data
│   ├── client.csv            # Client demographic and financial data
│   └── economics.csv         # Economic indicator data
├── notebook.ipynb            # Data-cleaning workflow
├── piggy_bank.jpg            # Project image
├── requirements.txt          # Python and Jupyter dependencies
└── README.md
```

## Output datasets

### `data/client.csv`

Contains client-level information:

- `client_id`
- `age`
- `job`
- `marital`
- `education`
- `credit_default`
- `mortgage`

### `data/campaign.csv`

Contains information about the current and previous marketing campaigns:

- `client_id`
- `number_contacts`
- `contact_duration`
- `previous_campaign_contacts`
- `previous_outcome`
- `campaign_outcome`
- `last_contact_date`

### `data/economics.csv`

Contains economic indicators associated with each client record:

- `client_id`
- `cons_price_idx`
- `euribor_three_months`

The original dataset, `bank_marketing.csv`, contains **41,188 records** and is retained in the `data/` directory for reference.

## Getting started

### Requirements

- Python 3
- Jupyter Notebook or JupyterLab
- The packages listed in [`requirements.txt`](requirements.txt)

### Installation

Create and activate a virtual environment, then install the dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

On Windows PowerShell, activate the environment with:

```powershell
.venv\Scripts\Activate.ps1
```

### Run the notebook

Start Jupyter:

```bash
jupyter notebook
```

Open `notebook.ipynb` and run the cells from top to bottom. The notebook reads the source data from `data/bank_marketing.csv` and writes the cleaned CSV outputs to the `data/` directory.

## Data notes

- Boolean fields are represented using the project’s cleaning rules: values such as `yes` or `success` are mapped to `1`, while other values are mapped to `0`.
- Missing or unknown education values are represented as missing data.
- The campaign date is constructed using the day and month fields together with the project-specified year of `2022`.
- The dataset is intended for data-cleaning and analysis practice; it should not be treated as a current banking or lending dataset.

## License

No license has been specified for this repository.
