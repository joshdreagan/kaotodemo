# Kaoto Demo - Solution

If you need to deploy a PostgreSQL DB

```
oc new-project postgresql
oc -n postgresql new-app --name cashback-db -e POSTGRESQL_USER=user1 -e POSTGRESQL_PASSWORD=Abcd1234 -e POSTGRESQL_DATABASE=public https://github.com/rh-cloud-architecture-workshop/cashback-db.git
```

Sample `curl` commands

```
curl -X POST -H 'Content-Type: application/json' -d '{"customerId": "avandelay", "customerName": "Art Vandelay"}' http://localhost:8080/customers

curl -X GET -H 'Accept: application/json' http://localhost:8080/customers
curl -X GET -H 'Accept: application/json' http://localhost:8080/customers/avandelay

curl -X PUT -H 'Content-Type: application/json' -d '{"customerName": "Arthur Vandelay"}'  http://localhost:8080/customers/avandelay

curl -X DELETE http://localhost:8080/customers/avandelay
```