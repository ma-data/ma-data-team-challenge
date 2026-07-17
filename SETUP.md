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

## 3. Launch a local DuckDB warehouse (Python)

[DuckDB](https://duckdb.org/docs/) is a local, file-based analytical database — a "warehouse" here
is just a file you create from Python. There's nothing to install or host beyond the pip packages
above. To spin one up and load the raw data:

```python
import duckdb

# Opens (and creates on first use) a local database file in the current folder.
con = duckdb.connect("warehouse.duckdb")

# DuckDB can read the raw files directly. Load each into a table:
con.execute("CREATE OR REPLACE TABLE raw_matches      AS SELECT * FROM read_csv_auto('data/matches.csv')")
con.execute("CREATE OR REPLACE TABLE raw_players      AS SELECT * FROM read_csv_auto('data/players.csv')")
con.execute("CREATE OR REPLACE TABLE raw_player_stats AS SELECT * FROM read_json_auto('data/player_stats.json')")

print(con.execute("SELECT COUNT(*) FROM raw_matches").fetchone())
con.close()
```

That `warehouse.duckdb` file is your warehouse — point dbt at it in the next step. (Want a throwaway
in-memory database for experiments instead? Call `duckdb.connect()` with no argument.)

- DuckDB Python client: <https://duckdb.org/docs/current/clients/python/overview.html>
- DuckDB documentation home: <https://duckdb.org/docs/>

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

- dbt-duckdb: <https://github.com/duckdb/dbt-duckdb>
- dbt docs: <https://docs.getdbt.com/>
