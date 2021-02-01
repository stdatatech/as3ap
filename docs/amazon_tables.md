亚马逊数据表

#### t_order
```
+-------------------------------------+--------------+------+-----+---------+-------+
| Field                               | Type         | Null | Key | Default | Extra |
+-------------------------------------+--------------+------+-----+---------+-------+
| amazon_order_id                     | varchar(255) | NO   | PRI | NULL    |       |
| assigned_ship_from_location_address | varchar(255) | YES  |     | NULL    |       |
| cba_displayable_shipping_label      | varchar(255) | YES  |     | NULL    |       |
| earliest_delivery_date              | varchar(255) | YES  |     | NULL    |       |
| earliest_ship_date                  | varchar(255) | YES  |     | NULL    |       |
| easy_ship_shipment_status           | varchar(255) | YES  |     | NULL    |       |
| fulfillment_channel                 | varchar(255) | YES  |     | NULL    |       |
| fulfillment_instruction             | varchar(255) | YES  |     | NULL    |       |
| is_business_order                   | bit(1)       | YES  |     | NULL    |       |
| is_estimated_ship_date_set          | bit(1)       | YES  |     | NULL    |       |
| is_global_express_enabled           | bit(1)       | YES  |     | NULL    |       |
| is_premium_order                    | bit(1)       | YES  |     | NULL    |       |
| is_prime                            | bit(1)       | YES  |     | NULL    |       |
| is_replacement_order                | bit(1)       | YES  |     | NULL    |       |
| is_sold_byab                        | bit(1)       | YES  |     | NULL    |       |
| last_update_date                    | varchar(255) | YES  |     | NULL    |       |
| latest_delivery_date                | varchar(255) | YES  |     | NULL    |       |
| latest_ship_date                    | varchar(255) | YES  |     | NULL    |       |
| marketplace_id                      | varchar(255) | YES  |     | NULL    |       |
| number_of_item_shipped              | int(11)      | NO   |     | NULL    |       |
| number_of_items_unshipped           | int(11)      | NO   |     | NULL    |       |
| order_channel                       | varchar(255) | YES  |     | NULL    |       |
| order_status                        | varchar(255) | YES  |     | NULL    |       |
| order_total                         | varchar(255) | YES  |     | NULL    |       |
| order_type                          | varchar(255) | YES  |     | NULL    |       |
| payment_execution_detail            | varchar(255) | YES  |     | NULL    |       |
| payment_method                      | varchar(255) | YES  |     | NULL    |       |
| payment_method_details              | varchar(255) | YES  |     | NULL    |       |
| promise_response_due_date           | varchar(255) | YES  |     | NULL    |       |
| purchase_date                       | varchar(255) | YES  |     | NULL    |       |
| replaced_order_id                   | varchar(255) | YES  |     | NULL    |       |
| sales_channel                       | varchar(255) | YES  |     | NULL    |       |
| seller_id                           | varchar(255) | YES  |     | NULL    |       |
| seller_order_id                     | varchar(255) | YES  |     | NULL    |       |
| ship_service_level                  | varchar(255) | YES  |     | NULL    |       |
| shipment_service_level_category     | varchar(255) | YES  |     | NULL    |       |
+-------------------------------------+--------------+------+-----+---------+-------+
```
#### t_order_item

```
+------------------------------+--------------+------+-----+---------+-------+
| Field                        | Type         | Null | Key | Default | Extra |
+------------------------------+--------------+------+-----+---------+-------+
| order_item_id                | varchar(255) | NO   | PRI | NULL    |       |
| amazon_order_id              | varchar(255) | YES  |     | NULL    |       |
| asin                         | varchar(255) | YES  |     | NULL    |       |
| cod_fee                      | varchar(255) | YES  |     | NULL    |       |
| cod_fee_discount             | varchar(255) | YES  |     | NULL    |       |
| condition_id                 | varchar(255) | YES  |     | NULL    |       |
| condition_note               | varchar(255) | YES  |     | NULL    |       |
| condition_subtype_id         | varchar(255) | YES  |     | NULL    |       |
| deemed_reseller_category     | varchar(255) | YES  |     | NULL    |       |
| gift                         | bit(1)       | YES  |     | NULL    |       |
| ioss_number                  | varchar(255) | YES  |     | NULL    |       |
| item_price                   | varchar(255) | YES  |     | NULL    |       |
| item_tax                     | varchar(255) | YES  |     | NULL    |       |
| points_granted               | varchar(255) | YES  |     | NULL    |       |
| price_designation            | varchar(255) | YES  |     | NULL    |       |
| product_info                 | varchar(255) | YES  |     | NULL    |       |
| promotion_discount           | varchar(255) | YES  |     | NULL    |       |
| promotion_discount_tax       | varchar(255) | YES  |     | NULL    |       |
| promotion_ids                | varchar(255) | YES  |     | NULL    |       |
| quantity_ordered             | int(11)      | NO   |     | NULL    |       |
| quantity_shipped             | int(11)      | NO   |     | NULL    |       |
| scheduled_delivery_end_date  | varchar(255) | YES  |     | NULL    |       |
| scheduled_delivery_start_dat | varchar(255) | YES  |     | NULL    |       |
| seller_id                    | varchar(255) | YES  |     | NULL    |       |
| sellersku                    | varchar(255) | YES  |     | NULL    |       |
| serial_number_required       | bit(1)       | YES  |     | NULL    |       |
| shipping_discount            | varchar(255) | YES  |     | NULL    |       |
| shipping_discount_tax        | varchar(255) | YES  |     | NULL    |       |
| shipping_price               | varchar(255) | YES  |     | NULL    |       |
| shipping_tax                 | varchar(255) | YES  |     | NULL    |       |
| tax_collection               | varchar(255) | YES  |     | NULL    |       |
| title                        | varchar(255) | YES  |     | NULL    |       |
| transparency                 | bit(1)       | YES  |     | NULL    |       |
+------------------------------+--------------+------+-----+---------+-------+
```

#### t_seller_sku
```
+--------+--------------+------+-----+---------+-------+
| Field  | Type         | Null | Key | Default | Extra |
+--------+--------------+------+-----+---------+-------+
| name   | varchar(255) | NO   | PRI | NULL    |       |
| asin   | varchar(255) | YES  |     | NULL    |       |
| cost   | double       | NO   |     | NULL    |       |
| enable | bit(1)       | NO   |     | NULL    |       |
+--------+--------------+------+-----+---------+-------+
```

#### t_inventory
```
+-------------------+--------------+------+-----+---------+-------+
| Field             | Type         | Null | Key | Default | Extra |
+-------------------+--------------+------+-----+---------+-------+
| asin              | varchar(255) | NO   | PRI | NULL    |       |
| kondition         | varchar(255) | YES  |     | NULL    |       |
| fn_sku            | varchar(255) | YES  |     | NULL    |       |
| inventory_details | text         | YES  |     | NULL    |       |
| last_update_time  | datetime     | YES  |     | NULL    |       |
| marketplace_id    | varchar(255) | YES  |     | NULL    |       |
| product_name      | varchar(255) | YES  |     | NULL    |       |
| seller_id         | varchar(255) | YES  |     | NULL    |       |
| seller_sku        | varchar(255) | YES  |     | NULL    |       |
| total_quantity    | int(11)      | YES  |     | NULL    |       |
+-------------------+--------------+------+-----+---------+-------+
```