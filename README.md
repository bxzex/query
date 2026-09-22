# Query

A real SQLite database, compiled to WebAssembly, running inside the browser tab.
Drop a CSV, write SQL against it, chart the result. Nothing is uploaded and
nothing is stored.

Live: https://bxzex.github.io/query/

## What it does

- **CSV import** — a hand written parser that handles quoted fields, embedded
  commas, escaped quotes and CRLF, with tab separated files detected from the
  header. Column types are inferred from the whole column, not the first row, so
  sorting and aggregates behave, and rows insert inside a single transaction
  through a prepared statement.
- **SQL** — the full SQLite dialect. Joins, window functions, CTEs, `pragma`.
  Cmd or Ctrl and Enter runs. Execution time is reported per query.
- **Charting** — the result columns pick the shape. The first non numeric column
  becomes the axis, the first numeric column becomes the series, and the chart
  hides itself when the result is not worth drawing.
- **Export** — any result set back out as CSV.
- **Sample warehouse** — 60 customers and 900 orders, generated from a seeded
  PRNG so the demo reads the same for everyone.

## Notes

One HTML file. The only dependency is `sql.js` from a CDN, which is SQLite
itself. No build step.

Built by [bxzex](https://bxzex.com).
