# Keytastrophe Keyboards

## Project Description

Keytastrophe keyboards is an important project because we as nerds love keyboards. Everyone in the modern era needs one of some kind as soon as they start to do work and we intend to capture \
the market. We will do this by ensuring a seemless and easy ordering process to get keyboards that people love and feel great into their hands. You need keyboards and we have them!

## Project Significance

Keytastrophe Keyboards enhances the typing experience by combining high-performance design with deep customization. By offering features like hot-swappable switches, customizable key mappings, \
and ergonomic layouts, our keyboards improve productivity and user satisfaction for gamers, professionals, and enthusiasts alike.

Beyond functionality, our focus on personalization fosters brand loyalty and engagement. With continuous innovation in wireless connectivity, switch technology, and intuitive software, \
Keytastrophe Keyboards sets new industry standards. By prioritizing quality and user experience, we establish ourselves as a leader in the competitive mechanical keyboard market.

## Business Requirements

Customer Management
a. Provide user credentialing for the online storefront.
b. Allow customers to create, customize, and order products.

Employee Management
a. Maintain a database of employees for business operations.
b. Track employee roles and responsibilities related to order processing and fulfillment.

Product Catalog & Inventory Management
a. Store and manage primary products, including keyboards and accessories.
b. Distinguish between main products, subcomponents, and accessories within the catalog.

Order Processing & Shipping Tracking
a. Track order status from placement to fulfillment.
b. Enable employees to update shipping progress as orders are processed and shipped.

E-Commerce & Shopping Cart System
a. Provide a seamless cart and checkout experience for customers.
b. Support multiple payment methods for easy transactions.

## Conceptual Diagram

![Digram](./conceptualDiagram.pdf)
## Conceptual Diagram Description 
<details>
<Summary>Entities & Descriptions</Summary> 
- Customer: A person browsing or purchasing products.<br>
- Customer Account: Credentialed profile for storefront access.<br>
- Order: A record of products purchased by a customer.<br>
-Shopping Cart: Temporary collection of products before checkout.<br>
- Cart Item: A specific product selected by the customer.<br>
- Payment Method: Credit card, PayPal, etc.<br>
- Order Status: Tracks progress (e.g., placed, packed, shipped).<br>
- Shipping Progress: Employee-updated record of shipping stages.<br>
- Employee: Person handling orders or managing catalog.<br>
- Role: Describes the employee's responsibilities (e.g., Fulfillment Specialist).<br>
- Department: Organizational group (e.g., Support, Fulfillment).<br>
- Product: Main items (keyboards) offered in the catalog.<br>
- Subcomponent: Switches, cases, PCBs used to build keyboards.<br>
- Accessory: Items like wrist rests, cables, lube kits.<br>
- Inventory: Stock tracking system.<br>
- User Credentialing: System managing customer logins.<br>
</details>
<details>
<summary>Attributes by Entity</summary>
▭ Customer <br>
customer_id, name, email <br>
▭ Customer Account<br>
account_id, username, password, preferences <br>
▭ Shopping Cart <br>
cart_id, created_date <br>
▭ Cart Item <br>
item_id quantity, added_date <br>
▭ Order <br>
order_id, date, total <br>
▭ Order Status <br>
status_id, timestamp, status (e.g., Placed, Shipped, Delivered) <br>
▭ Payment Method <br>
method_id, type (e.g., Credit Card, PayPal) <br>
▭ Employee <br>
employee_id, name, contact_info <br>
▭ Role <br>
role_id, title (e.g., Fulfillment Specialist, Customer Support) <br>
▭ Department <br>
department_id, name <br>
▭ Product <br>
product_id, name, price, category (e.g., Main, Subcomponent, Accessory) <br>
▭ Subcomponent <br>
subcomponent_id, name, type (e.g., Switch, PCB, Case) <br>
▭ Accessory <br>
accessory_id, name, compatible_with (types of products it's usable with)<br>
▭ Inventory <br>
inventory_id, product_id (foreign key), quantity <br>
▭ User Credentialing<br>
auth_id, auth_type (e.g., Email/Password, OAuth)<br>
</details>

<details>
<summary>RELATIONSHIPS (◇)</summary>
◇ Places <br>
Between ▭ Customer and ▭ Order <br>
Cardinality: Customer (1) — Places — (many) Order <br>
◇ Has<br>
Between ▭ Customer and ▭ Customer Account <br>
Cardinality: Customer (1) — Has — (1) Customer Account <br>
◇ Uses <br>
Between ▭ Customer and ▭ Shopping Cart <br>
Cardinality: Customer (1) — Uses — (many) Shopping Cart <br>
◇ Contains (Cart) <br>
Between ▭ Shopping Cart and ▭ Cart Item <br>
Cardinality: Shopping Cart (1) — Contains — (many) Cart Item <br>
◇ Contains (Order) <br>
Between ▭ Order and ▭ Product <br>
Cardinality: Order (1) — Contains — (many) Product <br>
◇ Has Status <br>
Between ▭ Order and ▭ Order Status <br>
Cardinality: Order (1) — Has — (many) Order Status entries over time <br>
◇ Paid With <br>
Between ▭ Order and ▭ Payment Method <br>
Cardinality: Order (1) — Paid With — (1) Payment Method <br>
◇ Processes <br>
Between ▭ Employee and ▭ Order <br>
Cardinality: Employee (many) — Processes — (many) Order <br>
◇ Updates <br>
Between ▭ Employee and ▭ Order Status <br>
Cardinality: Employee (many) — Updates — (many) Order Status <br>
◇ Assigned To <br>
Between ▭ Employee and ▭ Role<br>
Cardinality: Employee (1) — Assigned To — (many) Role(s) <br>
◇ Works In <br>
Between ▭ Employee and ▭ Department <br>
Cardinality: Employee (1) — Works In — (1) Department <br>
◇ Includes <br>
Between ▭ Product and ▭ Subcomponent <br>
Cardinality: Product (many) — Includes — (many) Subcomponent <br>
◇ Related To <br>
Between ▭ Product and ▭ Accessory <br>
Cardinality: Product (many) — Related To — (many) Accessory <br>
◇ Tracks <br>
Between ▭ Inventory and ▭ Product <br>
Cardinality: Inventory (1) — Tracks — (many) Product <br>
◇ Manages <br>
Between ▭ User Credentialing and ▭ Customer Account <br>
Cardinality: User Credentialing (1) — Manages — (many) Customer Account <br>
</details>
    
## Timeline

Week 1: Finalize Project Scope and Requirements

    1) Define detailed business requirements.
    2) Assign tasks to team members.
    3) Create a preliminary ER diagram to map out the database structure.

Week 2: Database Design

    1) Develop a detailed ER diagram and conceptual model.
    2) Design the relational schema, defining tables, attributes, and relationships.
    3) Establish primary keys, foreign keys, and normalization rules.
    4) Finalize schema and gather feedback.

Week 3: Implement the Database

    1) Set up the database.
    2) Create tables for
    3) Ensure data integrity and proper indexing.

Week 4: Develop Core Functionalities & Queries

    1) Implement queries for key transactions
    2) Develop logic for pricing adjustments and promotions.

Week 5: Testing & Debugging

    1) Perform unit and integration testing on all key functionalities.
    2) Test shopping cart and checkout workflows.
    3) Verify order fulfillment and inventory updates.
    4) Fix any issues related to data consistency, query performance, or functionality.

Week 6: Finalization & Documentation

    1) Finalize the database and optimize queries.
    2) Ensure reporting and analytics features work as expected.
    3) Prepare final project documentation (ER diagram, schema details, transaction logic).
    4) Complete the project report and presentation.

## Tentative Contribution

Due to the nature of being an online class and people having variable schedules hard deadlines will be hard to enforce on any given individual \
by the end of the project though we should expect that each member has given as much to the project as was reasonably expected of them. \
Ultimately everyone will be resposible for approximately 1 task per week and will be delegated at the top of the week and will be revisted at the \
end to ensure that timelines are met and we leave enough room for the role that life plays in ours lives.

## Group Members

Henry Hutchinson
Landon Whitney
Eric Parral
Andrew Storie
