# Query

SQLite running in your browser. Drop a CSV in, write SQL against it, and get a chart of the result.

https://bxzex.github.io/query/

The CSV parser is my own and handles quoted fields, embedded commas and CRLF. Column types are guessed from the whole column, not just the first row, so sorting works properly. Rows go in through one prepared statement inside a transaction, which keeps big files quick.

Cmd/Ctrl + Enter runs the query. If you just want to poke around, there's a sample warehouse with 60 customers and 900 orders.

The only dependency is sql.js, which is SQLite itself compiled to WebAssembly.
