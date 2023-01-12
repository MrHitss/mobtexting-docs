## OPTOUT

Traditionally, SMS campaigns are targeted to those customers who are registered subscribers to your SMS
services. You can block the customer's number using our optout feature. Once the customer's number is blocked, meanwhile if you try to trigger Sms to the customer's number then our system will automatically reject the Sms triggered and the customer will not recieve the sms.

#### API Endpoint

```
{domain}/api/{version}/
```

#### POST

```
{endpoint}sms/optout
```

#### MANDATORY PARAMETERS

| Name   | Descriptions                           |
| ------ | -------------------------------------- |
| number | Mobile numbers that you want to block. |

#### Example Request

```
curl -X POST \
  '{endpoint}sms/optout'
   -H 'Content-Type: application/x-www-form-urlencoded' \
   -H 'Accept: application/json' \
   -H 'Authorization: Bearer 38e896f55670311982434e929559xxxx'
   -F number=9174114xxxxx
```

On triggering the above API the specified numbers will be added to your optout list.

#### Example Response

```json
{
  'status': 'OK',
  'code': 200,
  'message': 'Number added to optout list',
  'data': {
    'mobile': '91998754****',
    'id': 'b45a89d7-5429-47fd-9275-b373f3f4****',
    'created_at': '2022-10-27T06:47:16.000000Z'
  }
}
```

## Delete Number from optout list

Delete number using delete method under your optout list

#### API Endpoint

```
{domain}/api/{version}/
```

#### DELETE

```
{endpoint}sms/optout/{number}
```

Replace the {number} with the actual number of the Mobile number that you would like to delete.

#### Example Request

```
curl -X DELETE \
  {endpoint}sms/optout/91873650xxxx \
  -H 'Authorization: Bearer 5b02112fb7xxxxxxxxxxxxxxx' \
```

#### Example Response

```json
{
  "status": "OK",
  "code": 200,
  "message": "Deleted successfully",
  "data": []
}
```