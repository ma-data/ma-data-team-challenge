# Setup

You'll need **Python 3.10+** and **git**. Everything runs locally — there's no cloud warehouse to
provision.

## 1. Environment

```bash
python -m venv .venv
# Windows:
.venv\Scripts\activate
# macOS / Linux:
source .venv/bin/activate

pip install -r requirements.txt
```

(Add any other libraries you want — this is just the minimum.)

## 2. The data

Raw files live in `data/`:

- `matches.csv` — one row per match (teams, date, score, season)
- `players.csv` — squad lists (player, team, position)
- `player_stats.json` — per-player, per-match stats (goals, assists, minutes, cards)

## 3. Warehouse (DuckDB)

[DuckDB](https://duckdb.org/docs/) is a local, file-based analytical database — nothing to install
or host beyond the pip packages above. Your ingestion code should create a DuckDB database (e.g.
`warehouse.duckdb` in the repo root) and load the raw data into it.

## 4. dbt (dbt-duckdb)

A minimal dbt project skeleton is in `dbt/`. To get going:

```bash
cd dbt
cp profiles.yml.example profiles.yml      # adjust the path if you put the db elsewhere
dbt debug  --profiles-dir .
dbt run    --profiles-dir .
dbt test   --profiles-dir .
```

Point your dbt **sources** at the raw tables your ingestion created, then build your staging and mart
models under `dbt/models/`. How you structure the ingestion and the models is entirely up to you —
that's part of what we're evaluating.

- dbt-duckdb docs: <https://github.com/duckdb/dbt-duckdb>
- dbt docs: <https://docs.getdbt.com/>
