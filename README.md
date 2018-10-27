# F5 Sites WooCommerce shop_orders Tables
by Francisco Mat

Hack plugin to make WordPress painless synching server instances database (aka: dev and production)

![F5 Sites WooCommerce shop_orders Tables](screenshot-shop_orders.png)

bunch update on WOOCOMMERCE core for FNETWORK COMPATIBILITY

==First: wpsql wordpress mysql plugin manager
We drasticly change the way we automate wp backup, so all order are stored separed in it own datastructure. All order are prefixed with 6woo_, so the table structure for orders are:

`
* 6woo_PREFIX_shop_order_post
* 6woo_PREFIX_shop_order_postmeta
* 6woo_PREFIX_woocommerce_order_items
* 6woo_PREFIX_woocommerce_order_itemmeta
`

In that way, to backup order from remote server, all we need to do is simples run

wpsql --import-prefixed 6woo_PREFIX

These was fundamental for speeding-up data backup and automatized backup process