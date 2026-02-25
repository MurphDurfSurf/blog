---
layout: post
---

### User Stories

Story One: Store Owner

    As the store owner, I’d like to add, edit, and remove groceries with name, price, description, quantity available, and manufacturer so customers can browse available inventory.

    Size would be 5 points and have no dependencies. Will allow for browsing and ordering functionality



Story Two: Customer Registration

	As a customer, I want to create an account using my name, address, and phone number so I can place orders to pick up or have delivered.

	Size would be 3 points, no dependencies, and would allow for order creation.

Story Three: Starting an Order

	As a now registered customer, I want to start a new order and choose pickup/delivery so the store knows how to fulfill it.

	Size is 3 points, depending on user story two.

Story Four: Add Items to Order

	As a registered customer making an order, I want to select groceries to add to my order with specified quantities, include special instructions, and indicate if substitution is allowed so my order follows my preferences.

	The size would be around 8 points and is dependent upon stories 1 and 3

Story 5: Finalize the Order

	As a customer, I want to choose a date/time for my order and finish my order so it can no longer be changed.

	The size of this story would be 5 points and depends solely on story 4.



With these stories in mind, we can now accurately construct a table schema for our store and figure out what needs to go where:


![Our grocery store table schema](/assets/images/Customer-diagram.png)


### Reflection

Designing this grocery store database required translating a real-world business scenario into a structured relational model. The most important decision was identifying the core entities and how they relate. I modeled five primary entities: Customer, Manufacturer, Item, Orders, and Order_Item. Although the prompt required only the manufacturer as an item attribute, I normalized it into its own entity. This prevents redundancy, enforces referential integrity, and supports future scalability if additional manufacturer data (such as contact information or contracts) is needed. Separating the manufacturer reflects a more realistic, properly normalized design.

A key structural challenge was modeling the relationship between orders and items. In practice, an order can include many items, and an item can appear in many orders. This is a classic many-to-many relationship. To represent it correctly, I created the associative entity Order_Item, which stores the quantity ordered, special instructions, and substitution preferences. These attributes belong to the relationship between an order and an item, not to the item itself. Without this table, the model would not capture customer customizations. This decision underscores why understanding relational modeling principles is essential when building database-backed applications.

However, real-world complications can arise when implementing this model. Inventory management can introduce race conditions if multiple customers attempt to purchase the last available item simultaneously. Price changes over time require storing historical pricing in the Order_Item table to preserve accurate transaction records. Fulfillment scheduling can also create conflicts if multiple customers select the same pickup or delivery time without capacity controls. While the current model handles the foundational relationships correctly, implementing it in a production environment would require additional logic and constraints to manage these edge cases effectively.

Overall, this project strengthened my understanding of how user stories translate into entity relationships and how business rules influence schema design. It reinforced the importance of normalization, associative entities, and referential integrity in creating scalable and realistic database systems.


