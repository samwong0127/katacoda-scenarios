## Test the endpoints

Open a new terminal

Run
`curl http://localhost:20080/store/stores`{{execute}}
to get all stores info

`curl http://localhost:20080/order/orders/00001/list`{{execute}}
to get the details of dishes in order: 00001

`curl http://localhost:20080/menu/stores/00001/menus`{{execute}}
to get the menu of store: 00001
etc.

If an error returns, try add a header by adding
`-i -H "Content-Type: application/json" -H "Accept: */*" -H "Connection: keep-alive" -H "Content-Type: application/json"`
in front of the link
