# Docker stack with keycloak, sample client app, saml provider

Based on this repo but with updated deps as well as mounts instead of builds:

https://github.com/vbhayden/keycloak-federation-examples

There are two static users configured in the IdP with the following data:

| UID | Username | Password | Group   | Email             |
| --- | -------- | -------- | ------- | ----------------- |
| 1   | user1    | user1pass | group1 | user1@example.com |
| 2   | user2    | user2pass | group2 | user2@example.com |

However you can define your own users by mounting a configuration file:

`-v /users.php:/var/www/simplesamlphp/config/authsources.php`

You can access the SimpleSAMLphp web interface of the IdP under http://localhost:8080/simplesaml. The admin password is `secret`.

You can access Keycloak admin interface via http://localhost:8081/admin. The user and password is `admin`

## Running

Bring stack up with `docker compose up -d`

Access example web application via `http://localhost:3000`, choose Simple SAML as login provider and login with a user in the table above.

