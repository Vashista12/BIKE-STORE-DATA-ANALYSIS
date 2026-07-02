# Bike Store Data Analysis — Power BI Dashboard 🚲

An interactive Power BI dashboard analyzing sales, revenue, and customer data for a multi-store bike retailer, built from a relational dataset spanning stores, products, orders, and customers.

## 📊 Dashboard Preview

<img width="605" height="338" alt="Screenshot 2026-07-01 134446" src="https://github.com/user-attachments/assets/d6a5b590-e5b4-40b2-9bcd-706567da5f70" />





## 🗂️ Dataset

The data is split across 8 related CSV files, modeled as a star schema in Power BI:

| File | Description |
|---|---|
| `orders.csv` | Order-level fact table — order date, status, store, staff, customer |
| `order_items.csv` | Line-item detail per order — product, quantity, list price, discount |
| `customers.csv` | Customer details — name, contact info, city/state |
| `products.csv` | Product catalog — name, brand, category, model year, list price |
| `brands.csv` | Brand lookup (e.g. Trek, Electra, Surly) |
| `categories.csv` | Product category lookup (e.g. Mountain Bikes, Road Bikes) |
| `stores.csv` | Store details — name, location, contact info |
| `staffs.csv` | Staff details, linked to store and manager |
| `stocks.csv` | Inventory quantity per product per store |

**Relationships:** `orders` and `order_items` form the core fact tables, joined to `customers`, `products`, `stores`, and `staffs`. `products` links out to `brands` and `categories`. `stocks` connects `products` and `stores` for inventory tracking.

## 📐 Key Metrics on the Dashboard

- **MTD Revenue** — month-to-date revenue
- **YTD Revenue** — year-to-date revenue
- **Total Revenue** — full dataset total
- **Total Customers** — distinct customer count
- **Revenue by Store Name** — comparing Baldwin Bikes, Santa Cruz Bikes, and Rowlett Bikes
- **Revenue by Year** — trend across 2016–2018
- **Revenue by Category Name** — split by product category and store
- **Revenue by Brand Name** — donut chart showing brand share (Trek, Electra, Surly, etc.)
- **City** — geographic breakdown with map visual

## 🎛️ Interactivity

- **Order Date slicer** — filter the whole report by a custom date range
- **City slicer** — filter by Baldwin, Rowlett, or Santa Cruz
- Cross-filtering between visuals (e.g. clicking a category filters the brand and store charts)

## 🛠️ Tools Used

- **Power BI Desktop** — data modeling, DAX measures, report design
- **Power Query** — importing and relating the 8 source tables

## 🚀 How to Use

1. Clone this repo
2. Open the `.pbix` file in Power BI Desktop
3. If prompted, update the data source file paths under **Transform Data → Data Source Settings** to point to your local copy of the CSVs
4. Refresh data

## 📌 Notes

- Revenue figures are calculated from `order_items` (`quantity × list_price`, adjusted for `discount`).
- Some fields in `customers.csv` (e.g. `phone`) contain `NULL` values — handled during data cleaning.

---

*Personal project built to practice data modeling and dashboard design in Power BI using a multi-table relational dataset.*
