# api_testing

🍽 Assignment 2 – “Restaurant Menu & Orders API”

Goal: Small real-world style API using relationships + tokens.

Requirements
Models

MenuItem

name, category (starter, main, dessert, drink), price, is_available

Order

id, customer_name, customer_phone, status (pending, completed, cancelled)

OrderItem

order_id, menu_item_id, quantity, unit_price

Auth

Use Sanctum.

Customers don’t need to register; one admin user can manage menu + see all orders.

Endpoints

Public:

GET /api/menu-items – list only is_available = true

GET /api/menu-items/category/{category}

Protected (auth:sanctum admin):

CRUD for /api/menu-items

GET /api/orders – list all orders

GET /api/orders/{id} – show order with its items

Semi-public (no auth, like restaurant app frontend):

POST /api/orders – create order with items
Request body includes customer info + array of items.

Extras / Bonus

Automatically calculate total price for an order.

Prevent ordering unavailable items.

📦 Assignment 3 – “Products API with Roles (Admin + Normal User)” (slightly advanced)

Goal: Practice guards + Sanctum + policies/middleware.

Requirements

Two guards:

admin (session + Sanctum tokens)

api/user (normal users via Sanctum)

Models: Admin, User, Product.

Public:

GET /api/products – list products

GET /api/products/{id} – show product

Admin (auth:sanctum with admin guard):

Full CRUD on products

User (auth:sanctum with user guard):

Can only view products, not create/update/delete.

Try enforcing this with:

policy
or

custom middleware that checks role/guard.
