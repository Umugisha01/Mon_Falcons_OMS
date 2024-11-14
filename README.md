# Mon_Falcons_OMS
# Mon_Falcons_OrderManagementSystem

# Online Service Delivery.

Customers can explore and add items to their cart when they enter the system. They can move on to the payment step if they choose to go forward with their purchase. They can, however, leave the system if the thing they're looking for isn't available. The customer can proceed on to the payment stage if they add many items to their cart. The processing and order arrangement department receives the order after it has been placed and verified. Here, a delivery person is allocated to the order based on availability after it was previously made.

After then, a secret code is assigned to the delivery package; the customer receives one half of the code and the delivery person receives the other half. After delivery, these codes must be entered in order to access the package. Customers are asked to assess their experience and submit feedback once the delivery has been confirmed. The management team then receives this input and examines it to see where the service needs to be improved.
 ## Uml Structure "Class Diagram"
 ![ORDER_DELIVERY_TRACKER](https://github.com/user-attachments/assets/af9868b8-aeab-4cb3-99ff-0d897fb1de72)

 
## Table Structures

### Customer Table

```sql
create table customer (
c_id int primary key,
f_name varchar(80) not null,
address varchar(50),
phone varchar(20) unique,
gender varchar(30) 
);
```
 
## Orders Table

```sql
create table orders (
o_id int primary key,
product_name varchar(100) not null,
QTY varchar (50),
price varchar(50) not null,
c_id int, 
foreign key(c_id) references customer(c_id)
);

```

## employee Table

```sql

create table Employee(
emp_id int primary key,
emp_name varchar(80) not null, 
Phone varchar(20) unique,
salary varchar(40) default '30000rwf',
o_id int, foreign key(o_id) references orders(o_id)
);
```

## products Table

```sql
create table product (
product_id int primary key ,
product_name varchar(80) not null,
price_at_supplier varchar (100) not null,
retail_price varchar(80) not null, 
stock_available varchar(20) not null,
safety_stock int ,
emp_id int, 
foreign key (emp_id) references employee(emp_id));

```
## ERD STRUCTURE
<img width="618" alt="ERD" src="https://github.com/user-attachments/assets/4084b2f3-8f99-4352-bb1f-f62557966ad2">

