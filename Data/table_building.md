## Adding Tables to the Database


**Actor Table**
```SQL 
CREATE TABLE actor(
		 actor_id int
	    ,first_name varchar(50)
	  	,last_name varchar(50)
	 	,last_update timestamp
);
```

```SQL 
COPY actor
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\actor.csv'
DELIMITER ','
CSV Header;
```


**Actor_info Table**
```SQL
CREATE TABLE actor_info(
		 actor_id int
	    ,first_name varchar(50)
	  	,last_name varchar(50)
	 	,film_info text
);
```

```SQL
COPY actor_info
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\actor_info.csv'
DELIMITER ','
CSV Header;
```

**Address Table**
```SQL
CREATE TABLE address(
		 address_id int
	    ,address varchar(250)
	  	,address2 varchar(250)
	 	,district varchar(50)
	 	,city_id int
 		,postal_code int 
 		,phone varchar(50)                                          
);
```

```SQL
SET client_encoding = WIN1252;

COPY address
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\address.csv'
DELIMITER ','
CSV Header;
```

**Category Table**
```SQL 
CREATE TABLE category(
		 category_id int
	    ,category_name varchar(20)
	  	,last_update timestamp                                        
);
```

```SQL
COPY category
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\category.csv'
DELIMITER ','
CSV Header;
```

**City Table**
```SQL
CREATE TABLE city(
		 city_id int
	    ,city varchar(50)
		,country_id int
	  	,last_update timestamp                                        
);
```

```SQL
COPY city
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\city.csv'
DELIMITER ','
CSV Header;
```

**Country Table**
```SQL
CREATE TABLE country(
		 country_id int
		,country varchar(250)
	  	,last_update timestamp                                        
);
```

```SQL
COPY country
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\country.csv'
DELIMITER ','
CSV Header;
```

**Customer Table**
```SQL 
CREATE TABLE customer(
		 customer_id int
 		,store_id int
		,first_name varchar(50) 
		,last_name varchar(50)   
		,email varchar(250)
		,address_id int
		,active boolean
		,create_date timestamp      
		,last_update timestamp
);
```

```SQL
COPY customer
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\customer.csv'
DELIMITER ','
CSV Header;
```

**Customer_list Table**
```SQL
CREATE TABLE customer_list(
		 customer_id int
 		,customer_name  varchar(100)                
	 	,address varchar(250)             
 		,zip_code int
 		,phone varchar(20) 
 		,city varchar(50)           
		,country varchar(50)
		,notes varchar(10)
		,SID int
);
```

```SQL
COPY customer_list
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\customer_list.csv'
DELIMITER ','
CSV Header;
```

**Film Table**
```SQL
CREATE TABLE film(
		 film_id int
		,title varchar(100)                      
		,description text                                                                                                                  
		,release_year int
		,language_id int
		,rental_duration int
		,rental_rate money
		,film_length int
		,replacement_cost money 
		,rating varchar(10)
		,special_features varchar(250)                                      
		,last_update timestamp
);
```

```SQL
COPY film
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\film.csv'
DELIMITER ','
CSV Header;
```

**Film_list Table**
```SQL
CREATE TABLE film_list(
		 fid int
		,title varchar(50)                     
		,description text
		,category varchar(20)
		,price money
		,film_length int 
		,rating varchar(10)
		,actors text
);
```

```SQL
COPY film_list
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\film_list.csv'
DELIMITER ','
CSV Header;
```

**Film_actor Table**
```SQL
CREATE TABLE film_actor(
		 actor_id int
 		,film_id  int                
	 	,last_update timestamp             
);
```

```SQL
COPY film_actor
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\film_actor.csv'
DELIMITER ','
CSV Header;
```

**Film_category Table**
```SQL
CREATE TABLE film_category(
		 film_id int
 		,category_id  int                
	 	,last_update timestamp             
);
```

```SQL
COPY film_category
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\film_category.csv'
DELIMITER ','
CSV Header;
```

**Film_text Table**
```SQL
CREATE TABLE film_text(
		 film_id int
 		,title varchar(100)               
	 	,description text           
);
```

```SQL
COPY film_text
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\film_text.csv'
DELIMITER ','
CSV Header;
```

**Inventory Table**
```SQL
CREATE TABLE inventory(
		 inventory_id int
 		,film_id int              
	 	,store_id int
		,last_update timestamp
);
```

```SQL
COPY inventory
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\inventory.csv'
DELIMITER ','
CSV Header;
```


**Language Table**
```SQL
CREATE TABLE film_language(
		 language_id int
 		,language_name varchar(10)              
		,last_update timestamp
);
```

```SQL
COPY film_language
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\language.csv'
DELIMITER ','
CSV Header;
```

**Payment Table**
```SQL
CREATE TABLE payment(
		 payment_id int
		,customer_id int
		,staff_id int
		,rental_id int
		,amount money
		,payment_date timestamp        
		,last_update timestamp
);
```

```SQL
COPY payment
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\payment.csv'
DELIMITER ','
CSV Header;
```

**Rental Table**
```SQL
CREATE TABLE rental(
		 rental_id int
		,rental_date timestamp         
		,inventory_id int
		,customer_id int
		,return_date timestamp     
		,staff_id int
		,last_update timestamp        
);
```

```SQL
COPY rental
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\rental.csv'
DELIMITER ','
CSV Header;
```

**Sales_by_film_category Table**
```SQL
CREATE TABLE sales_by_film_category(
		 category varchar(20)
		,total_sales money              
);
```

```SQL
COPY sales_by_film_category
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\sales_by_film_category.csv'
DELIMITER ','
CSV Header;
```

**Sales_by_store Table**
```SQL
CREATE TABLE sales_by_store(
		 store varchar(20)
		,manager varchar(20) 
		,total_sales money
);
```

```SQL
COPY sales_by_store
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\sales_by_store.csv'
DELIMITER ','
CSV Header;
```

**Staff Table**
```SQL
CREATE TABLE staff(
		 staff_id int
		,first_name varchar(10)
		,last_name varchar(10)
		,address_id int
		,email varchar(250)
		,store_id int
		,active boolean
		,username varchar(10)
		,login_password varchar(250)                            
		,last_update timestamp
);
```

```SQL
COPY staff
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\staff.csv'
DELIMITER ','
CSV Header;
```

**Staff_list Table**
```SQL
CREATE TABLE staff_list(
		 staff_id int
		,staff_name varchar(50)       
		,address varchar(250)
		,zip_code int
		,phone bigint       
		,city varchar(20)       
		,country varchar(20)
		,SID int
);
```

```SQL
COPY staff_list
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\staff_list.csv'
DELIMITER ','
CSV Header;
```

**Store Table**
```SQL
CREATE TABLE store(
		 staff_id int
		,manager_staff_id int
		,address_id int 
		,last_update timestamp         
);
```

```SQl
COPY store
FROM 'C:\Users\akobe\OneDrive\Desktop\Lighthouse\After\SQL-book-learning\Data\store.csv'
DELIMITER ','
CSV Header;
```