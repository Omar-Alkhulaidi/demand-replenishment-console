# Methodology

## 1. Data Preparation

The project uses enterprise-style supply chain and inventory data covering:

- Historical sales
- Product hierarchy
- Inventory levels
- Lead times
- Revenue
- Store and regional information

Data preparation was performed using Power Query.

---

## 2. Data Modeling

The model follows a dimensional structure with dedicated dimensions for:

- Product
- Store
- Calendar

and a central fact table containing sales and inventory activity.

This structure allows analytical measures to operate consistently across different time periods, products, stores, and regions.

---

## 3. Demand Analysis

Demand analysis combines historical sales behavior with inventory availability.

Key metrics include:

- Actual Demand
- Average Daily Sales
- Forecasted Demand
- Forecast Variance
- Forecast Accuracy
- Days of Supply

---

## 4. ABC Classification

Products are dynamically classified according to their cumulative contribution to revenue.

The classification supports prioritization of inventory management activities.

---

## 5. Replenishment Logic

The replenishment module uses inventory planning concepts to determine when and how much to reorder.

### Reorder Point

Reorder Point is calculated using:

`ROP = Demand During Lead Time + Safety Stock`

### Suggested Order Quantity

The suggested quantity is calculated based on the gap between the replenishment target and current inventory position.

---

## 6. Decision Support

The final output is intentionally divided into two workflows:

### Planning

Understand demand, inventory trends, and forecast behavior.

### Execution

Identify SKUs requiring action and determine suggested order quantities.

This separation reduces information overload and creates a clearer workflow for different supply chain users.
