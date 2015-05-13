# Reservations

## Get All Reservations

```shell
curl "https://app.hotelrunner.com/api/v1/apps/reservations?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint updates the room.

### HTTP Request

`GET https://app.hotelrunner.com/api/v1/apps/reservations`

### Query Parameters

Parameter | Default | Required | Description
------------ | ------ | ------- | -----------
**token** | - | Yes | Will be provided by property.
**hr_id** | - | Yes | Will be provided by property.
**from_date** | Begining of last month | No | Format: YYYY-MM-DD`. If provided, reservations after this date will be retrieved.
**per_page** | 10 | No | Number of reservations per page.
**page** | 1 | No | Number of current page.
**reservation_number** | - | No | Used to get a specific reservation. It can be whether HotelRunner or Channel reservation code.
