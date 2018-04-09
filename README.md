# Intro

*This documentation gathers IDwall's official API information.*

Navigate through the complete documentation here: https://github.com/idwall/idwall-api-en-us/wiki

### What does IDwall do?

IDwall exists to securely streamline and automate your *onboarding process* for new users, customers or partners via* Background Check*.

Our system queries a variety of public and private sources, bringing you information as custom reports that can help you approve and enroll more people on your platform. This entire process is automatic, and can be done through our [Dashboard] (https://dashboard.idwall.co) or our API.

### How to Use This Documentation

While following this documentation, we recommend that you use [Postman] (https://www.getpostman.com/). In it you will import the *Collection* from IDwall using the *Import > Import from Link* menu* https://api-v2.idwall.co/postman.
The article [Import API documentation v2 through Postman] (https://intercom.help/idwall/api/testes-da-api/importar-add-up-api-v2-traves-of-postman) explains the step-by-step process.

### API usage

We use a [REST API] (https://pt.wikipedia.org/wiki/REST). We follow a common pattern among all *endpoints* for greater predictability:
- All requests executed successfully return ```HTTP Status 200```.
- Failed requests will return the status number relevant to the error, as well as keys with extra information about this error.
- We use [query parameters] (https://en.wikipedia.org/wiki/Query_string) as aid for pagination, filters and additional information that can be requested in the query.
- All requests return JSON (application/json) content and have standard bodies:


### Success requests

```json
{
    "status_code": 200,
    "result": { }
}
```

### Failed requests

```json
{
    "status_code": 404,
    "error": "Not Found",
    "message": "O protocolo requisitado não foi encontrado."
}
```

Each endpoint has a different *schema* for the `result` field, which can be queried
as required in the course of this documentation.

Our *endpoint* basis for implementation is:


```
https://api-v2.idwall.co
```

The *endpoints* shown throughout the documentation should be used at the end of the *endpoint* base. For example, the *endpoint* ```/validacoes``` is accessed through the URL ```https://api-v2.idwall.co/validacoes```


The ```header``` of all requests must contain the key:

```json
{
  "Authorization": "{token}",
}
```

where ```{token}``` is your user's access key. Your access key can be found by visiting our Dashboard at [https://dashboard.idwall.co/conta](https://dashboard.idwall.co/conta).
