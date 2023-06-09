# General information

Project created as a part of acceptance exam of europebet

## Program information

console-based ecommerce application that includes the following commands:

- save_product
- purchase_product
- order_product
- get_quantity_of_product
- get_average_price
- get_product_profit
- get_fewest_product
- get_most_popular_product
- exit

## constraints

- does not store data persistently, though optionally writes some data to file
- expects that parameters given to it will be of valid types and valid quantity

## Commands:

- `save_product {product_id} {product_name} {product_price}`:
    - Add a new product to the catalog or modify an existing one.
    - Example: `save_product prod001 iphone 2800`

- `purchase_product {product_id} {quantity} {price}`:
    - Purchase a product, increasing its balance based on the specified quantity.
    - Example: `purchase_product prod001 10 2500`

- `order_product {product_id} {quantity}`:
    - Place an order for the product, decreasing its balance according to the specified quantity.
    - Example: `order_product prod001 3`

- `get_quantity_of_product`:
    - Return the remaining quantity of a specific product.
    - Example: `get_quantity_of_product prod001` (Returns `7`)

- `get_average_price {product_id}`:
    - Calculate and display the average price of a specific product based on its purchase history.
    - Scenario: You purchased 10 phone001 for 2000 and later purchased 30 more phone001 for 3000. The average price of
      phone001 is 2750 based on the purchase history.
    - Example: `get_average_price prod001` (Returns `2750`)

- `get_product_profit {product_id}`:
    - Calculate and display the profit earned from a specific product by comparing the average purchase price with the
      average order price.
    - Scenario: You purchased 10 phones for 2000 and later purchased 30 more phones for 3000. Then, you sold 5 phones
      for 3500, 10 phones for 3800, and 15 phones for 4000. Average purchase price – 2750; average order price – 4500;
      profit per unit – 1750; total profit - 52500.
    - Example: `get_product_profit prod001` (Returns `52500`)

- `get_fewest_product`:
    - Return the name of the product with the lowest remaining quantity.
    - Example: `get_fewest_product` (Returns `iphone`)

- `get_most_popular_product`:
    - Return the name of the product with the highest number of orders.
    - Example: `get_most_popular_product` (Returns `iphone`)

  `generate_orders_report`:
    - Generate a report of all orders, including the product ID, product name, quantity,
      price, cost of goods sold (COGS), and selling price.

  `export_orders_report`:
    - Export the report of all orders to a CSV
      file at the specified file path.

- `exit`:
    - Close the console application.

## Docker

Include a Dockerfile with the appropriate configuration in your solution folder to enable your application to run in
Docker.

To build and run your project using Docker, execute the following command:

```console
docker build -t ecommerceapp . && docker run --rm -i ecommerceapp

