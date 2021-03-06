# money transfer RESTful API
A Java RESTful API for money transfers between users accounts

Using:

- JAX-RS API
- H2 in memory database
- Log4j 
- Jetty Container (for Test and Demo app)
- Apache HTTP Client
 



## How to run demo app

Clone from GitHub:
```
git clone https://github.com/lambhotpot/MoneyTransferRESTfulAPI.git
```

Build the project after performing unit tests and integration tests:
```
mvn clean test install
```

Executing Demo App:
```
mvn exec:java
```






The demo app starts a jetty server on localhost port 8083
An H2 in memory database initialized with some sample user and account data
To view them use the below URL from browser: 
```
http://localhost:8083/money-app/user/yangluo
http://localhost:8083/money-app/user/qinfran
http://localhost:8083/money-app/account/1
http://localhost:8083/money-app/account/2
http://localhost:8083/money-app/account/3
http://localhost:8083/money-app/account/4
```


# Available Services


| HTTP METHOD        | PATH           |  USAGE |
| ------------- |:-------------|:-----|
| GET     | /user/{userName} | get user by user name |
| GET     | /user/all  |   get all users |
| PUT     | /user/create     |  create a new user |
| POST    | /user/{userId} | update user |
| DELETE  | /user/{userId}     | remove user |
| GET     | /account/{accountId} | get account by accountId |
| GET     | /account/all  |   get all accounts |
| GET     | /account/{accountId}/balance  |   get account balance by accountId |
| PUT     | /account/create     |  create a new account |
| DELETE  |/account/{accountId}     | remove account by accountId |
| PUT     | /account/{accountId}/withdraw/{amount}    |  withdraw money from account |
| PUT     | /account/{accountId}/deposit/{amount}     |  deposit money to account |
| POST    | /transaction    |  perform transaction between 2 user accounts |


## Http Status 

```
200 OK: The request has succeeded
```

```
400 Bad Request: The request could not be understood by the server 
```

```
404 Not Found: The requested resource cannot be found
```

```
500 Internal Server Error: The server encountered an unexpected condition 
```

## Sample JSON for User and Account

##### User:
 ```json
{  
   "userName":"yangluo",
   "emailAddress":"yangluo@gmail.com"
} 
```

##### User Account:
```json
{  
   "userName":"yangluo",
   "balance":10.0000,
   "currencyCode":"GBP"
}
```

##### User Transaction:
```json
{  
   "currencyCode":"EUR",
   "amount":100000.0000,
   "fromAccountId":3,
   "toAccountId":4
}
```

## Future Improvements

- Enriched functionality on transaction with fx involved
- Persist user transactions
- Exception handling and error code enhancement
- More Java Docs, Comments, test cases on edge cases
- Adding more logs for monitoring and performance analysis



