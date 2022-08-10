# PAAYS AUTO API Version 1.0 (Closed Beta)

## Note - 
This API is in closed beta. To access the endpoints please connect with the Paays team.  

## Get Transaction by using user details

Use this API call to obtain the details of a consumer based on conversation ID or user details. 

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction-details`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction-details -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"userDetails":{"firstName": "dev","lastName": "test","phoneNo": "6472273539","drivingLicenseNumber": "xyz"}}'

### Response

    
```
{
    "status": 1,
    "data": {
        "transaction": {
            "date": "2022-08-04",
            "time": "20:30:27"
        },
        "dlInfo": {
            "full_name": "DIRK J VANDERPLAAT",
            "given_names": "DIRK",
            "middle_name": "J",
            "family_name": "VANDERPLAAT",
            "gender": "M",
            "phoneNumber": "4167884343",
            "date_of_birth": "1963-02-12",
            "age": "59",
            "date_of_issue": "2021-06-08",
            "expiration_date": "2026-02-12",
            "document_number": "V03961715630212",
            "document_type": "DL",
            "issuing_authority": "CA-ON",
            "structured_postal_address": {
                "street_address": "110 RIDLEY BLVD",
                "city_address": "TORONTO",
                "province_name": "ON",
                "postal_code": "M5M3L9",
                "formatted_address": "110 RIDLEY BLVD,TORONTO,CA,ON,M5M3L9"
            }
        },
        "dlCheck": {
            "action": "accept",
            "flags": []
        },
        "fraudCheck": {
            "active": "Y",
            "deviceRiskScore": 0.1,
            "ipAddress": "174.95.80.9",
            "geoLocation": "-79.3877, 43.7012",
            "city": "Toronto",
            "country": "Canadá",
            "emailFirstSeen": null,
            "emailAge": null,
            "emailRiskScore": null,
            "bureauHit": null,
            "bureauFraudFlag": null,
            "fraudCheckDescision": null
        }
    }
}
```
## Get Transaction by using routeone (conversationId)

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction-details`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction-details -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"conversationId":"PAA-1-PREQFDDD3951"}'

### Response

    ```
    {
    "status": 1,
    "data": {
        "transaction": {
            "date": "2022-08-04",
            "time": "20:30:27"
        },
        "dlInfo": {
            "full_name": "DIRK J VANDERPLAAT",
            "given_names": "DIRK",
            "middle_name": "J",
            "family_name": "VANDERPLAAT",
            "gender": "M",
            "phoneNumber": "4167884343",
            "date_of_birth": "1963-02-12",
            "age": "59",
            "date_of_issue": "2021-06-08",
            "expiration_date": "2026-02-12",
            "document_number": "V03961715630212",
            "document_type": "DL",
            "issuing_authority": "CA-ON",
            "structured_postal_address": {
                "street_address": "110 RIDLEY BLVD",
                "city_address": "TORONTO",
                "province_name": "ON",
                "postal_code": "M5M3L9",
                "formatted_address": "110 RIDLEY BLVD,TORONTO,CA,ON,M5M3L9"
            }
        },
        "dlCheck": {
            "action": "accept",
            "flags": []
        },
        "fraudCheck": {
            "active": "Y",
            "deviceRiskScore": 0.1,
            "ipAddress": "174.95.80.9",
            "geoLocation": "-79.3877, 43.7012",
            "city": "Toronto",
            "country": "Canadá",
            "emailFirstSeen": null,
            "emailAge": null,
            "emailRiskScore": null,
            "bureauHit": null,
            "bureauFraudFlag": null,
            "fraudCheckDescision": null
        }
    }
}


## Create Transaction

Use this API call to create a ID Verify link that will be sent by a dealer to a end consumer, to start the IDV process. 

### Request

`POST https://uat-developer.preq.ai/api/v1/transaction`

    curl -X POST https://uat-developer.preq.ai/api/v1/transaction -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'apikey: REYrtBoxeLvf1iYLis3fuK4lPlXohokEVhn6VXeBYBk=' -d '{"userDetails":{"firstName": "test","lastName": "user","phoneNo": "6472273539","email": "test.user@yopmail.com", "dealerEmail": "dealer@yopmail.com"}}'

### Response

    {"status":1,"link":"dealer. Please click on this link to verify your identity. https://dealer-dev.preq.ai/verify/?phoneNumber=6472273539&dealerEmail=dealer@yopmail.com","message":"link sent successfully"}
