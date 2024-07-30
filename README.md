# Order-Payment
It's the sales order &amp; payment data real time ingestion.

Python Package For Installation
-------------------------------

pip3 install google-cloud-pubsub
pip3 install cassandra-driver

Docker command to start cassandra
----------------------------------

docker compose -f docker-compose-cassandra.yml up -d

* Once cassandra container started, open the terminal of docker container
* type cqlsh on terminal
* cqlsh shell will be opened and now cassandra related commands can be executed

Cassandra table Creation
-------------------------------

CREATE KEYSPACE IF NOT EXISTS ecom_store WITH REPLICATION = { 'class' : 'SimpleStrategy', 'replication_factor' : 1 };

CREATE TABLE ecom_store.orders_payments_facts (
    order_id BIGINT PRIMARY KEY,
    customer_id BIGINT,
    item TEXT,
    quantity BIGINT,
    price DOUBLE,
    shipping_address TEXT,
    order_status TEXT,
    creation_date TEXT,
    payment_id BIGINT,
    payment_method TEXT,
    card_last_four TEXT,
    payment_status TEXT,
    payment_datetime TEXT
);

