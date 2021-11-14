## Test the endpoints

Open a new terminal

Run

`curl http://localhost:20080/menu/menus`{{execute}}
to show all the menus.

`curl http://localhost:20080/menu/stores/00001/menus`{{execute}}
to get the menu of store: 00001.

`curl -i -H "Content-Type: application/json" -H "Accept: */*" -H "Connection: keep-alive" -H "Content-Type: application/json" -X POST -d '{"store_id":"12345", "store_name":"A store", "dishes_id":"12345", "dishes_name":"A dish", "price":10, "avaliability":true}' http://localhost:20080/menu/stores/12345/menus`{{execute}}
to create or update the menu for a specific store.

`curl -i -H "Content-Type: application/json" -H "Accept: */*" -H "Connection: keep-alive" -H "Content-Type: application/json" -X POST -d '{"store_id":"00001", "store_name":"A store", "dishes_id":"00001", "dishes_name":"A dish", "price":10, "avaliability":true}' http://localhost:20080/menu/stores/00001/menus/dishes/00001`{{execute}}
to update an individual item within a menu.

`curl -X DELETE http://localhost:20080/menu/stores/00001/menus/dishes/00001`{{execute}} to delete an individual item within a menu.

`curl http://localhost:20080/order/orders`{{execute}}
to show all orders.

`curl http://localhost:20080/order/orders/00001/list`{{execute}}
to get the details of dishes in order: 00001

`curl -i -H "Content-Type: application/json" -H "Accept: */*" -H "Connection: keep-alive" -H "Content-Type: application/json" -d '{"store_id":"00001", "dishes_id":"00001", "dishes_name":"A dish", "price":10, "avaliability":true}' -X POST http://localhost:20080/order/addorder/stores/00001`{{execute}}
to add an order for store: 00001.

`curl -X DELETE http://localhost:20080/order/deleteorder/orders/00001`{{execute}}
to delete an order with order ID 00001.

`curl http://localhost:20080/store/stores`{{execute}}
to get all stores info

`curl http://localhost:20080/store/stores/00001`{{execute}}
to get info of store with ID 00001.

`curl http://localhost:20080/store/stores/category/Japanese`{{execute}}
to get all attributes of a store with a specific category

If an error returns, try add a header by adding
`-i -H "Content-Type: application/json" -H "Accept: */*" -H "Connection: keep-alive" -H "Content-Type: application/json"`
in front of the link

Here is all our API endpoints:
### Menu 
- Return a JSON object with all attributes of all menu sort by menu_id:
    - GET ``/menus`` 
- Return a JSON object with all the menus’ attributes of a store:
    - GET ``/stores/<store_id>/menus`` 
- Create or update the entire menu for a specific store:
    - POST ``/stores/<store_id>/menus`` 
- Updates an individual item within a menu:
    - POST ``/stores/<store_id>/menus/dishes/<dishes_id>``
- Delete an individual item within a menu:
    - DELETE ``/stores/<store_id>/menus/dishes/<dishes_id>``

### Order 
- Return a JSON object with all attributes of all orders:
    - GET ``/orders``
- Return a JSON object with all the orders’ attributes of a orderID:
    - GET ``/orders/<order_id>/list``
- Add an order for a specific store:
    - POST ``/addorder/stores/<storeID>``
- Delete an order for a specific store:
    - DELETE ``/deleteorder/orders/<OrderID>``

### Store 
- Return a JSON object with all attributes of all store sort by store_id:
    - GET ``/stores``
- Return a JSON object with all attributes of a specific store:
    - GET ``/stores/<store_id>``
- Return a JSON object with all attributes of a store with a specific category:
    - GET ``/stores/category/<categories>``