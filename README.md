# db_gen

A Python script to generate **synthetic e-commerce datasets**, ideal for testing DuckDB, analytics pipelines, and data processing tools.

## Features
- Generates **Customers**, **Products**, **Orders**, **Order Items**, and **Product Reviews**.
- Saves data in **CSV** and **Parquet** formats.
- **Auto-installs** required Python packages if missing.
- Adjustable dataset sizes via CLI arguments.
- `--quick` flag for instant small-sample generation.

---
## Entity Relationship Diagram
![](EDR.png)
---

## Installation
Clone the repository:
```bash
git clone https://github.com/naelaqel/db_gen.git
cd db_gen
```

Requires **Python 3.8+**.  
No need to manually install dependencies — the script will install them automatically.

---

## Usage

### 1. Default mode (large datasets for stress testing)
```bash
python db_gen.py
```
**Default sizes:**
| Dataset         | Rows       |
|-----------------|-----------:|
| Customers       | 1,000,000  |
| Products        | 10,000     |
| Orders          | 4,000,000  |
| Order Items     | 10,000,000 |
| Reviews         | 2,000,000  |

---

### 2. Quick mode (small datasets for instant testing)
```bash
python dataset_generator.py --quick
```
**Quick mode sizes:**
| Dataset         | Rows  |
|-----------------|------:|
| Customers       | 100   |
| Products        | 10    |
| Orders          | 200   |
| Order Items     | 500   |
| Reviews         | 100   |

---

### 3. Custom mode (set your own sizes and output folder)
```bash
python dataset_generator.py \
    --customers 5000 \
    --products 300 \
    --orders 2000 \
    --order-items 8000 \
    --reviews 1500 \
    --path ./data
```

---

## Output
The script saves two folders inside the specified output path:

```
csv/       # CSV files
parquet/   # Parquet files
```

---

## Dependencies
Installed automatically if missing:
- `Faker` — generate realistic fake data
- `pandas` — data handling
- `numpy` — numeric operations
- `pyarrow` — Parquet file support

---

## License
MIT License
