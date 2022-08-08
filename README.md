# PAAYS AUTO APIs

## Get Transaction by using user details

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction-details`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction-details -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"userDetails":{"firstName": "dev","lastName": "test","phoneNo": "6472273539","drivingLicenseNumber": "xyz"}}'

### Response

    {"status":1,"data":{"customerUid":"broad-slowly","transactionId":"5910470497402880","refreshToken":"95UWcmx8ICPFYU6ZmpuHuO-fOXXhktWs","phoneNumber":"6472273539","dealerEmail":"david@frycars.com","userIpAddress":"103.59.75.111","maxmindReport":null,"countryCode":"CA","createdAt":"2022-06-17T07:36:33.684Z","updatedAt":"2022-07-14T10:21:27.037Z","data":{"user":{"documentNumber":"xyz"}},"hrfaReport":null,"active":true}}

## Get Transaction by using routeone (conversationId)

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction-details`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction-details -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"conversationId":"PAA-1-PREQFDDD3951"}'

### Response

    {"status":1,"data":{"customerUid":"broad-slowly","transactionId":"5910470497402880","refreshToken":"95UWcmx8ICPFYU6ZmpuHuO-fOXXhktWs","phoneNumber":"6472273539","dealerEmail":"david@frycars.com","userIpAddress":"103.59.75.111","maxmindReport":null,"countryCode":"CA","createdAt":"2022-06-17T07:36:33.684Z","updatedAt":"2022-07-14T10:21:27.037Z","data":{"user":{"documentNumber":"xyz"}},"hrfaReport":null,"active":true}}

## Create Transaction

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"userDetails":{"firstName": "test","lastName": "user","phoneNo": "6472273539","email": "test.user@yopmail.com", "dealerEmail": "dealer@yopmail.com"}}'

### Response

    {"status":1,"link":"dealer. Please click on this link to verify your identity. https://dealer-dev.preq.ai/verify/?phoneNumber=6472273539&dealerEmail=dealer@yopmail.com","message":"link sent successfully"}