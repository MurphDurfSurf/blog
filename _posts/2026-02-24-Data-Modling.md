---
layout: post
---

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


![Our grocery store table schema](/CSCI340Lab2Fork/assets/css/PNGs/Blankdiagram.png)

