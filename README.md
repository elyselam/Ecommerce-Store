# Staging Database
## Tables


- CUSTOMERS
	- CUSTOMER_ID (text, primary key): key to the orders dataset. Each order has a unique customer_id.
	- CUSTOMER_UNIQUE_ID (text): unique identifier of a customer
	- rice(integer): first five digits of customer zip code
	- CUSTOMER_CITY (text): customer city name
	- CUSTOMER_STATE (text): customer state

- GEOLOCATION
	- GEOLOCATION_ZIP_CODE_PREFIX (int): first five digits of customer zip code
	- GEOLOCATION_LAT (float): latitude 
	- GEOLOCATION_LNG (float): longitude
	- GEOLOCATION_CITY (text): city name
	- GEOLOCATION_STATE (text): state


- ORDER_ITEMS
	- ORDER_ID (text): product unique identifier
	- ORDER_ITEM_ID (int): sequential number identifying number of items included in the same order
	- PRODUCT_ID (text): product unique identifier
	- SELLER_ID  (text): seller unique identifier
	- SHIPPING_LIMIT_DATE (text): Shows the seller shipping limit date for handling the order over to the logistic partner
	- PRICE (float): item price
	- FREIGHT_VALUE (float): item freight value item (if an order has more than one item the freight value is splitted between items)


- PAYMENTS
	- ORDER_ID (text): unique identifier of an order
	- PAYMENT_SEQUENTIAL (int): a customer may pay an order with more than one payment method. If he does so, a sequence will be created to accommodate all payments
	- PAYMENT_TYPE (text): method of payment chosen by the customer
	- PAYMENT_INSTALLMENTS (int): number of installments chosen by the customer
	- PAYMENT_VALUE (float): transaction value 

- ORDER_REVIEWS
	- REVIEW_ID (text): unique review identifier
	- ORDER_ID (text): unique order identifier
	- REVIEW_SCORE (int): Note ranging from 1 to 5 given by the customer on a satisfaction survey
	- REVIEW_COMMENT_TITLE (text): Comment title from the review left by the customer, in Portuguese
	- REVIEW_COMMENT_MESSAGE (text): Comment message from the review left by the customer, in Portuguese
	- REVIEW_CREATION_DATE (text): Shows the date in which the satisfaction survey was sent to the customer
	- REVIEW_ANSWER_TIMESTAMP (text): Shows satisfaction survey answer timestamp

- ORDERS
	- ORDER_ID (text): unique identifier of the order
	- CUSTOMER_ID (text, primary key): key to the customer dataset, each order has a unique customer_id
	- ORDER_STATUS (text): Reference to the order status (delivered, shipped, etc)
	- ORDER_PURCHASE_TIMESTAMP (text): Shows the purchase timestamp
	- ORDER_APPROVED_AT (text): Shows the payment approval timestamp
	- ORDER_DELIVERED_CARRIER_DATE (text): Shows the order posting timestamp. When it was handled to the logistic partner
	- ORDER_DELIVERED_CUSTOMER_DATE (text): Shows the actual order delivery date to the customer
	- ORDER_ESTIMATED_DELIVERY_DATE (text): Shows the estimated delivery date that was informed to customer at the purchase moment

- PRODUCTS:
	- PRODUCT_ID (text): unique product identifier
	- PRODUCT_CATEGORY_NAME (text): root category of product, in Portuguese
	- PRODUCT_NAME_LENGTH (int): umber of characters extracted from the product name
	- PRODUCT_DESCRIPTION_LENGTH (int): number of characters extracted from the product description
	- PRODUCT_PHOTOS_QTY (int): number of product published photos
	- PRODUCT_WEIGHT_G (int): product weight measured in grams
	- PRODUCT_LENGTH_CM (int): product length measured in centimeters
	- PRODUCT_HEIGHT_CM (int): product height measured in centimeters
	- PRODUCT_WIDTH_CM (int): product width measured in centimeters

- SELLERS
	- SELLER_ID (text): seller unique identifier
	- SELLER_ZIP_CODE_PREFIX (int): first 5 digits of seller zip code
	- SELLER_CITY (text): seller city name
	- SELLER_STATE (text): seller state


- CATEGORY_NAME_TRANSLATION
	- PRODUCT_CATEGORY_NAME (text): category name in Portuguese
	- PRODUCT_CATEGORY_NAME_ENGLISH (text): category name in English



## Warehouse Database

### Dimensions
- PRODUCTS_D
	- _ID3
	
- CUSTOMERS_D
	- _ID1
	- _ID4
	- _ORDER_ID3
	- PRICE
	- TAXES
	
- GEOLOCATIONS_D
	- _ID
	- LAT
	- LON
	
### Fact Table
- GENERAL_F
	- _ID1
	- _ID2
	- _ID3
	- _ID4
	- TOTAL_COST
	- TIMESTAMP
	





















