
# MIST 4610 Group Project

Group 21479_9

Rishitha Cheemarla - https://github.com/rishitha-cheemarla/rishitha

Peyton McWhorter - https://github.com/pem83470/Group-9

Andrew Smith - https://github.com/andrewmsjr/Andrew-Smith-4610-Group-9

Somya Tailang -

Ava Weichel - https://github.com/avaweichel/avaweichel/blob/main/README.md


## Problem Description

One of the problems that we are trying to solve within this diagram is to make a reservation system for our restaurants and also keep track of the loyalty of our customers. Almost every popular restaurant has the problem of not having enough space or equipment to acquire a certain amount of customers during their hours. We created a data model to highlight how a reservation system would benefit the restaurant in terms of maintaining a certain amount of people in the restaurant at a time with the number of employees and customers we have. This can be shown in the data model within the reservation entity. We also want to keep track of which customers are the most loyal to our restaurant business as doing so will allow us to serve those better and improve the quality of our restaurant. We did this by creating a loyalty program that can be indicated by our Membership and Customer entities within the data model. As can be seen in the Membership entity, we have attributes such as membershipID and points which will indicate which member/customer is most loyal to our restaurant so we can give them rewards and serve them better. Another problem we wanted to solve was maintaining and tracking employee shift records. This is vital for restaurants to understand their employee bandwidth, hours, and common shifts. 
## Data Model 

![App Screenshot](https://raw.githubusercontent.com/andrewmsjr/Andrew-Smith-4610-Group-9/main/Screen%20Shot%202023-03-31%20at%201.00.40%20PM.jpeg)

The data model provided is the corresponding model for the restaurant database. The model shows the back-end relationships between entities for the database. The model portrays the relationships between each location, employees, customers, orders, and everything for the restaurant overall. 

The location entity stores information about every location of the restaurant. It stores data about the name and where each individual location is found. The location entity is related to the shift entity via a one-to-many relationship. This relationship is due to the fact that one location can have many instances of a work shift. The shift entity is related to the employee table. The employee table stores information about a certain location’s employees. It is related to shift also by a one-to-many relationship. An employee can have many shifts, but each instance of shift only has one employee. Additionally within the employee table, exists a one-to-many relationship. This recursive one-to-many relationship refers to the fact that a manager, who is also an employee, manages many employees, but these employees have only one manager. 

The employee table is related to the reservation table via a one-to-many relationship. The reservation table stores information about each individual reservation participant from the employee to the customer and order. The relationship between the two entities is based on the fact that an employee can create many reservations, but a reservation can only be handled by one employee. The reservation table is also related to the customer table. The customer table contains customer information and is related to reservation with a one-to-many relationship. A customer may place multiple reservations, but each individual instance of a reservation will have only one customer. The customer table is also related to the membership table by a one-to-one relationship. The membership table stores information about the customers who are members of the loyalty program for the restaurant. The relationship is based on the fact that each membership will only have one customer and vice versa for each customer having only one membership. 

The employee table is related to the order entity. The order entity stores details about each order that is processed in the restaurant. This relationship is formed by an order being processed by one employee, but one employee can process many orders. Reservation is also related to the order table but with a one-to-one relationship. This one-to-one relationship is based on a reservation order or the order that is placed under a certain reservation. The customer table, like the employee table, is related to order using a one-to-many relationship. A customer may place many orders, but a specific instance of an order will only go to one customer. 

The order table is related to the menu item table via a many-to-many relationship. This relationship between order and menu item creates the entity, amount ordered. Amount ordered is an entity that stores composite information where each instance of amount ordered is defined by the order and menu item together. The menu item entity stores information about each item that appears on the menu like the name and cost. The menu item table is related to the ingredient table via another many-to-many relationship. This many-to-many relationship creates the recipe entity. The recipe table, like the amount ordered table, stores composite information about which ingredients correspond to which menu item. The ingredient entity stores information about the ingredients that get purchased by the restaurant. It stores information about their name, cost, and how much is left in stock.

## Data Dictionary

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Screen%20Shot%202023-03-31%20at%201.31.36%20PM.png)

![Logo](https://raw.githubusercontent.com/rishitha-cheemarla/rishitha/main/Screen%20Shot%202023-03-31%20at%201.36.41%20PM.png)

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Screen%20Shot%202023-03-31%20at%201.39.03%20PM.png)

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Screen%20Shot%202023-03-31%20at%201.40.13%20PM.png)
## 10 Queries

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q1.png)

For this query we demonstrated a recursive relationship from our data model shown in the Employee table. By duplicating the Employee table and renaming one “Manager” and the other “Managed” and joining the two we were able to find the employeeIDs that were also present as managerIDs. This query groups those managerIDs and also counts the number of employeeIDs that are managed by each manager present in the table. Knowing who is a manager and how many employees they manage is important and can be used for decision making purposes. 

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q2.png)

This query lists the cost of an ingredient and the menu item name if the ingredient goes into one of the menu items containing the word “chicken” in the name. This is shown by joining the Ingredient entity onto the Recipe entity and then Recipe onto MenuItem. This join allows access to the data under the MenuItem.name and Ingredient.cost attributes. Then by adding the REGEXP “Chicken” we are pulling all MenuItems that have chicken in the title. By grouping menu item then cost we are able to see the costs associated with each menu item with chicken in the name. This information is important because it can be used when making pricing decisions.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q3.png)

This query counts and groups the number of  reservations and number of people on a given date. Including this query would be helpful from a managers perspective because it would allow them to have an estimate on how to delegate responsibilities for servers and hosts. It would also allow the kitchen to estimate how much food they would need to have prepared for the night to best eliminate waste. Knowing the reservation details allows staff to have the restaurant and tables prepared ahead of time, ultimately minimizing stress.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/q4.png)

This query finds the number of employees who work on a given day and calculates the number of hours they worked on that day. This is helpful from a managers perspective because it allows them to be able to have the correct amount of hours for the payroll. It makes calculating paychecks easier, since all staff are paid on an hourly basis. Once managers have daily hours worked, they can add up total hours in a pay period and multiply that by hourly rates. We divided the summation of the endTime-startTime by 10000 because it was in military time on our data and computed large numbers. 

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q5.png)

This query calculates and returns the ratio, expressed as a percentage, of the average salary for each specific job title compared to the average salary of all employees when the average salary for a job title is less than the average salary for all employees. This particular query would be useful to a manager for them to identify employees who are making less than the average employee and what percentage of the average salary they are making. That information would be useful in determining pay scales for employee job titles as well as help incentivise higher performance from employees with job titles that have above average pay scales. Since they are paid more, more is expected of them.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q6.png)

This query finds and returns the customer who has the most points out of all customers. This query is useful since identifying the customer who has the highest points is likely one of, if not the top, customers. It would provide the manager an opportunity to create a personal relationship with a top customer in order to try and continue to keep their trust and gain their business. It could also be useful in determining the top prize in a contest or sweepstakes. At the end of a defined time period, the customer who has the most points would be eligible for a reward provided by the restaurant.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q7.png)

This query finds the percentage of all customers that specifically have more than 400 points as part of their membership. This query is useful as it allows one to see which customers are the most loyal to the restaurant. This query would be important for letting the manager know whether a customer should be given a reward, such as free dessert or a discount, for their loyalty to the restaurant. Finding out the percentage of this would let the managers and restaurant owners analyze how many customers in general are regular and can make changes from there if they want more customers to reach that 400 threshold.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q8.png)

This query prints the job title and name of the employee who works specifically at the Georgia restaurant location. Our data model emphasizes the fact that our restaurant business has several locations around the country. By selecting jobTitle, first name, and last name from employees, we get the result of a bartender that works at the Georgia location along with their first and last name. This is convenient as it will tell which employees are in Georgia and can contact them accordingly for any purpose. We can use the first and last name of the employee to further obtain their contact information like phone number or email.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q9.png)

This query lists out the first and last name of employees with the job title “host” who have taken reservations. By selecting first name and last name from employees and adding an exists clause where we get a boolean true when employeeID shows up in both reservation and employee, we are able to see which employees have taken a reservation. This is important because we can track which employees have taken a reservation and if they are being efficient in this sense or not.

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/Q10.png)

This query shows the number of employees that get off work before 5PM in GA, SC, FL, and AL. This is useful for restaurants who need to pull regional employees who work the early shift or get off before the dinner shift. This information lets the manager know if they are overstaffed during the morning shift or help them understand what shift appeals more to their staff.

## Query Metrics

![Logo](https://github.com/rishitha-cheemarla/rishitha/raw/main/query%20metric.png)