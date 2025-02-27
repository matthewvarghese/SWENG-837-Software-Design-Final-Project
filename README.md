# SWENG-837-Software-Design-Final-Project

1.	UML Use Case Diagram:
   

Customer interacts with the system by doing actions like logging in, browsing products, adding products to the cart, and proceeding to checkout. These are the usual interactions a customer with any kind of ecommerce system.

Admin: The admin user has a different set of permissions, including modifying products and managing orders. The Admin would be me alone.

Stripe is an external system used for making payments securely during checkout. 



2.	UML Domain Model:


User class represents any user of the shop. Each user can have multiple orders and one cart. This is standard for an online shop.

Products represents an item in the clothing store. Products can be added to both the cart and the order.

Cart contains the list of products that a user is going to buy. It is associated with a user with their login and it can have multiple products.

Order is for when a user completes the checkout process, an order is created. An order contains a list of products and keeps track of the total price.




3.	UML Class Diagram:
 

User Class: Stores user data such as id, email, password, and profile information. Its methods include login(), register(), and updateProfile().

Product Class: Represents individual products with attributes like id, name, price, and description. It's methods are addProduct(), updateProduct(), and deleteProduct() allow product management.

Cart Class: Contains a list of products selected by the user. The methods are addProduct(), removeProduct(), and checkout() handle cart operations.

Order Class: Once the checkout process is complete, an order is created. It contains the list of products in the order, and the total amount. The methods are createOrder(), cancelOrder(), and viewOrder().



4.	UML Sequence Diagrams:
 

Customer starts interacting with the Frontend and then requests product details from the Backend. The customer can also add products to the cart and then go to checkout.

Frontend sends updates to the Backend for cart information, order validation, and checkout procedure.

Backend validates the cart, calculates total price, and calls Stripe to make the payment. Once payment is confirmed, the Backend finalizes the order and confirms the process with the Frontend.

Stripe handles the payment methods and sends the payment confirmation to the Backend.



5.	UML State Diagram:
   
New
The order is created but payment is still pending from stripe.

Payment Pending
 The payment is being processed with stripe.

Paid
 The payment is successful and the order is ready for shipping.

Shipped
 The order is shipped to the customer.

Delivered
 The order is delivered to the customer.



6.	UML Activity Diagram (Swimlane Diagram):
 

Theres 3 parts for this diagram in swimlanes. Customer browses the products, adds them to the cart, and then proceeds to checkout on stripe.
System will validates the cart, processes payment, and creates the order.
Stripe will then processes payment and sends back the confirmation to the system



7.	UML Component Diagram:

For the component diagram, the Frontend handles the user interface, allowing the customer to interact with the website, browse for products, and manage their cart items. 
The Backend manages the business logic which is user authentication, product management, and order processing. 
The Stripe component handles payment processing and authentication.

   


8.	Cloud Deployment Diagram:
 
For the Deployment Diagram, the Frontend is hosted on Netlify which providing fast and scalable delivery of the user interface.
The Backend is deployed on Heroku, which handles server-side logic and database operations.
Heroku was a great choice for me as it was simple and cheap. It's about 6 dollars a month. The Stripe component is an external service hosted in the cloud for 


