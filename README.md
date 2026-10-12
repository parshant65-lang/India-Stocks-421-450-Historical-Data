# India-Stocks-421-450-Historical-Data

Institutional Historical 1-Minute Market Data Archive for **India Equities (Constituents 421 to 450)** with automated daily cloud capture via GitHub Actions.

---

## 🏛️ Directory Hierarchy

```text
India-Stocks-421-450-Historical-Data/
├── .github/workflows/daily_ingest.yml
├── fetch_batch.py
├── README.md
├── <SYMBOL>/
│   └── 1m/
│       ├── README.md
│       └── <YYYY>/
│           └── <MM>/
│               ├── <SYMBOL>_1m_<YYYY-MM-DD>.csv
```

---

## ⏰ 4-Tier Automated Schedule (Mon–Fri)

| Trigger | Time (IST) | Cron (UTC) | Role |
|:---|:---:|:---:|:---|
| **Primary Trigger** | **15:45 IST** | `15 10 * * 1-5` | 15 mins post-market close |
| **Backup Trigger 1** | **16:45 IST** | `15 11 * * 1-5` | 1 hour safety net |
| **Backup Trigger 2** | **17:45 IST** | `15 12 * * 1-5` | 2 hours safety net |
| **Backup Trigger 3** | **18:45 IST** | `15 13 * * 1-5` | 3 hours safety net |

---

## 📦 Constituents (421 to 450)

| # | Symbol | Company Name | Yahoo Ticker |
|---|---|---|---|
| 421 | `PARADEEP` | Paradeep Phosphates Ltd. | `PARADEEP.NS` |
| 422 | `PETRONET` | Petronet LNG Ltd. | `PETRONET.NS` |
| 423 | `PWL` | Physicswallah Ltd. | `PWL.NS` |
| 424 | `PINELABS` | Pine Labs Ltd. | `PINELABS.NS` |
| 425 | `PPLPHARMA` | Piramal Pharma Ltd. | `PPLPHARMA.NS` |
| 426 | `POLYMED` | Poly Medicure Ltd. | `POLYMED.NS` |
| 427 | `POONAWALLA` | Poonawalla Fincorp Ltd. | `POONAWALLA.NS` |
| 428 | `PFOCUS` | Prime Focus Ltd. | `PFOCUS.NS` |
| 429 | `PRIVISCL` | Privi Speciality Chemicals Ltd. | `PRIVISCL.NS` |
| 430 | `RRKABEL` | R R Kabel Ltd. | `RRKABEL.NS` |
| 431 | `RBLBANK` | RBL Bank Ltd. | `RBLBANK.NS` |
| 432 | `RHIM` | RHI MAGNESITA INDIA LTD. | `RHIM.NS` |
| 433 | `RITES` | RITES Ltd. | `RITES.NS` |
| 434 | `RAILTEL` | Railtel Corporation Of India Ltd. | `RAILTEL.NS` |
| 435 | `RAINBOW` | Rainbow Childrens Medicare Ltd. | `RAINBOW.NS` |
| 436 | `RKFORGE` | Ramkrishna Forgings Ltd. | `RKFORGE.NS` |
| 437 | `REDINGTON` | Redington Ltd. | `REDINGTON.NS` |
| 438 | `RPOWER` | Reliance Power Ltd. | `RPOWER.NS` |
| 439 | `RUBICON` | Rubicon Research Ltd. | `RUBICON.NS` |
| 440 | `SJVN` | SJVN Ltd. | `SJVN.NS` |
| 441 | `SHRIPISTON` | SPR Auto Technologies Ltd. | `SHRIPISTON.NS` |
| 442 | `SAGILITY` | Sagility Ltd. | `SAGILITY.NS` |
| 443 | `SAILIFE` | Sai Life Sciences Ltd. | `SAILIFE.NS` |
| 444 | `SAMMAANCAP` | Sammaan Capital Ltd. | `SAMMAANCAP.NS` |
| 445 | `SANSERA` | Sansera Engineering Ltd. | `SANSERA.NS` |
| 446 | `SARDAEN` | Sarda Energy and Minerals Ltd. | `SARDAEN.NS` |
| 447 | `SCHAEFFLER` | Schaeffler India Ltd. | `SCHAEFFLER.NS` |
| 448 | `SCHNEIDER` | Schneider Electric Infrastructure Ltd. | `SCHNEIDER.NS` |
| 449 | `SCI` | Shipping Corporation of India Ltd. | `SCI.NS` |
| 450 | `SHREECEM` | Shree Cement Ltd. | `SHREECEM.NS` |


---

## ⚡ 1-Line Pandas Stream Loader

```python
import pandas as pd

# Example: Stream PARADEEP 1m data
url = "https://raw.githubusercontent.com/parshant65-lang/India-Stocks-421-450-Historical-Data/main/PARADEEP/1m/2026/10/PARADEEP_1m_2026-10-12.csv"
df = pd.read_csv(url)
print(df.head())
```
