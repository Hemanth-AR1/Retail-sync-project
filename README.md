[ Client Browser / Web UI ]
            |
            v
[ Streamlit App Server ]
    |-- URL Routing Engine (?server=srv_1 | srv_2 | srv_3)
    |-- Cached Connection Pool (@st.cache_resource)
    |
    |-- PostgreSQL Client (psycopg2)
    |   |-- orders (Transactional Ledger)
    |   |-- billing (Invoice Records)
    |   |-- inventory (Stock Quantities)
    |   `-- Cross-Table SQL Joins (Unpaid Invoices)
    |
    `-- MongoDB Client (pymongo)
        |-- products (BSON Product Catalog)
        `-- reviews (BSON Feedback Collection)
