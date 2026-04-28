# ABC Foodmart — ETL Pipeline

Python + PostgreSQL ETL pipeline that loads a normalized 19-table operational
schema for ABC Foodmart, a 5-store grocery chain in Queens and Brooklyn, NY.

## Stack
- PostgreSQL 15+
- Python 3.10+ (psycopg2, Faker)
- Jupyter

## Files
- `abc_foodmart_load_data_v2.ipynb` — the full ETL loader

## How to run
1. Create the database and run the schema DDL (`schema.sql`)
2. Edit `DB_CONFIG` in cell 1 of the notebook with your Postgres credentials
3. Run all cells

The loader is seeded (`random.seed(42)`) so output is byte-identical across runs.

## Row counts after load
| Domain      | Rows           |
|-------------|----------------|
| Workforce   | 5 / 12 / 89    |
| Products    | 20 / 91 / 455  |
| Procurement | 15 / 159 / 665 / 1,622 / 1,407 |
| Sales       | 600 / 10 / 109 / 3,021 / 15,197 |
| Finance     | 9 / 600 / 2,848 |

See the accompanying ETL report for full design rationale.
