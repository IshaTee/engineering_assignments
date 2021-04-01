##Assignment for Frontend Developer.##

Soko is an omnichannel commerce platform that enables a business to quickly set up and run an online retail store.

A typical seller installs the Dukaan app, Signs up using his mobile number and creates his store. He can then start uploading inventory (as products) to his store. Once the store is created, he can share the store link with his/her customers on social media and starts accepting online orders.

Your assignment is to Design a very basic API (Django DRF) & database (PG) structure which supports above work-flow.

Detailed breakdown of the workflow -
endpoints for seller side. (Words in Bold indicates table names)
seller signs up using his mobile number that creates an account

Take mobile number & OTP (random) as input to the API
Create customer account in accounts table.
Issue a token.
seller creates his store

Take store name & address as input.
Create store in store table. One customer can have multiple stores.
Generate a unique store link based on his store name.
Respond back with storeid and link.
seller starts uploading inventory in the form of products and seller.

Take product name, description, MRP, Sale price, image & category as input.
Create a category if it doesn't exist.
Create product
Respond back with id, name and image.
Seller can accept orders from his customers.

Create a customer table with a mobile number as unique and address details.
Create a order table to store orders data.
When someone places an order from the buyer side, the records will be saved here.
Endpoints for Buyer side
Seller shares his store link with his customers. To get basic store details

Take store link as input
Respond back with storeId, store name, address
To get product catalog & categories

Take storelink as input
Respond back with the catelog, grouped by categories & sorted by number of products in the category.
people (Un-authenticated users) can add items into their cart.

Maintain a cart on the server in either DB or redis or MongoDb
On cart change (add / remove item) update the cart on server
For cart line items take product id, qty, storeLink as input and fetch product meta data from the DB and save them.
Customer place an order for a product.

Identity customer using JWT or token which can be generated using his mobile number and a OTP
Bypass the actual OTP validation flow and issue a token on any random number & OTP combination
Create a customer record if didn’t already exist for that mobile number.
Take the cart object as input and convert that into an order.
Create an order for that store & customer and return back the order id.
