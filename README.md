# si
Create a modern web-based inventory and sales management system inspired by the functionality and simplicity of Billz. This is a WEBSITE ONLY for now, not a mobile app.

The main purpose of the system is to manage products, inventory, barcode/QR scanning, sales, and stock levels.

1. Dashboard

Create a clean professional dashboard showing:

* Total number of products
* Total items currently in stock
* Total inventory value
* Today’s sales
* Today’s revenue
* Low-stock products
* Out-of-stock products
* Recent sales

Use cards, simple charts, and tables. The interface should be fast, minimal, and easy for a shop employee to understand.

2. Products / Inventory

Create a Products section where users can:

* Add a new product
* Edit product
* Delete product
* Search products
* Filter products
* View product details
* See current stock quantity
* See purchase price
* See selling price
* See barcode
* See QR code if available
* See total inventory value

When adding a product, include:

* Product name
* Product image
* Category
* Barcode
* QR code
* Purchase price
* Selling price
* Quantity
* Minimum stock level

The system must calculate inventory value automatically:

Inventory Value = Quantity × Purchase Price

3. Barcode / QR Scanner

Add a prominent “Scan” button.

The website should use the device camera to scan:

* EAN/UPC barcodes
* QR codes

After scanning a code:

1. Search the database for the matching barcode/QR code.
2. If the product exists, display its information immediately.
3. If the product does not exist, show an option to create a new product using the scanned code.

The scanner must work well on smartphones, tablets, and desktop computers with a camera.

4. Add Product Through Scanner

Create a workflow:

Scan barcode → Product not found → “Add Product”

Automatically fill the barcode field with the scanned code.

The user then enters:

* Product name
* Category
* Purchase price
* Selling price
* Quantity

Then save the product to the database.

5. Sales Section

Create a dedicated “Sales” page.

The sales page should look like a simple POS interface.

At the top:

* Large barcode/QR scanner button
* Search product field

When a product is scanned:

Show:

* Product name
* Product image
* Selling price
* Available stock
* Quantity being sold

Allow the cashier to add multiple products to the current sale.

Example:

Product A — $10 × 2
Product B — $15 × 1

Automatically calculate:

* Subtotal
* Total quantity
* Total price

6. Complete Sale

Add a large “Complete Sale” button.

When the sale is successfully completed:

* Save the sale to the database.
* Decrease the stock quantity for every sold product.
* For one sold item: quantity = quantity - 1.
* For two sold items: quantity = quantity - 2.
* Update the dashboard immediately.
* Update the product inventory immediately.
* Add the transaction to Sales History.

Example:

Before sale:
Product quantity = 10

Customer buys 1:

After successful sale:
Product quantity = 9

IMPORTANT: Stock must NOT decrease if the sale is cancelled or fails.

7. Sales History

Create a Sales History page.

Show:

* Sale ID
* Date
* Time
* Products sold
* Quantity
* Total amount
* Status

Allow users to open a sale and see its full details.

Add filters:

* Today
* Yesterday
* This week
* This month
* Custom date range

8. Low Stock System

Automatically detect products below their minimum stock level.

Show them in:

* Dashboard
* Products page
* Low Stock page

Use clear visual warnings.

If quantity reaches 0, mark the product as “Out of Stock”.

9. Database

Use a real persistent database, not temporary mock data.

Create at minimum these entities:

PRODUCTS:

* id
* name
* image
* category
* barcode
* qr_code
* purchase_price
* selling_price
* quantity
* minimum_stock
* created_at
* updated_at

SALES:

* id
* total_amount
* total_quantity
* status
* created_at

SALE_ITEMS:

* id
* sale_id
* product_id
* quantity
* price
* subtotal

When a sale is completed, update the PRODUCTS quantity and create the corresponding SALES and SALE_ITEMS records.

Use proper database transactions so inventory cannot become inconsistent.

10. Design

The design should be:

* Modern
* Premium
* Minimal
* Professional
* Similar in usability to modern POS/inventory platforms
* Responsive
* Desktop-first but fully usable on mobile
* Clean sidebar navigation

Sidebar:

Dashboard
Products
Inventory
Sales
Sales History
Low Stock
Settings

Use a white/light interface with optional dark mode.

Do NOT copy Billz’s exact branding, logo, colors, or UI. Only take inspiration from the general simplicity and workflow of professional inventory/POS software.

11. Important UX

Make the most important actions extremely fast:

Scan → Find Product → Add to Sale → Complete Sale → Stock Automatically Decreases

A cashier should be able to complete a sale in only a few clicks.

Add loading states, success notifications, error messages, empty states, confirmation dialogs, and validation.

For example:

“Sale completed successfully”

“Stock updated: iPhone Case - 9 remaining”

If a scanned product is out of stock:

“Product is out of stock”

Do not allow the user to sell more units than are currently available.

12. Technical Requirements

Build this as a functional website, not just a static design.

All buttons and pages must work.

Use real database CRUD operations.

Implement real barcode/QR camera scanning.

Implement real inventory calculations.

Implement real sales transactions.

Make the application responsive.

Seed the database with several example products so the website can be tested immediately.

The final result should feel like a real small-business inventory + POS system that could later be expanded into a full SaaS product.