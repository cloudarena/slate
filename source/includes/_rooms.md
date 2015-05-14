# Rooms (Property)

## Get Room List

```shell
curl "https://app.hotelrunner.com/api/v1/apps/rooms?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
[

  {
    "code": "HR_1",
    "name": "Standard Room",
    "description": "Standard Room Description",
    "policy": "Standard Room Policy",
    "room_capacity": 3,
    "adult_capacity": 2
  },
  {
    "code": "HR_2",
    "name": "Double Room",
    "description": "Double Room Description",
    "policy": "Double Room Policy",
    "room_capacity": 2,
    "adult_capacity": 2
  }
]
```

This endpoint retrieves all rooms of property.

### HTTP Request

`GET https://app.hotelrunner.com/api/v1/apps/rooms`

### Room Object

Name | Description
------------ | ------
**code** | Room code on HotelRunner
**name** | Name of room
**description** | Description of room
**policy** | Free text policy for room
**room_capacity** | Maximum room capacity including children
**adult_capacity** | Maximum adult count that can stay in room


## Update Room


```shell
curl -X PUT --data "hr_id={HR_ID}&token={TOKEN}&vid={ROOM_CODE}&start_date={START_DATE}&end_date={END_DATE}&availability={AVAILABILITY}&price={PRICE}&min_stay={MIN_STAY}&stop_sale={STOP_SALE}" https://app.hotelrunner.com/api/v1/apps/rooms/~
```

> The above command returns text structured like this:

```text
'ok' for success, 'try_again' for fail.
```


This endpoint updates the room.


`PUT https://app.hotelrunner.com/api/v1/apps/rooms/~`

### Query Parameters

Parameter | Default | Required | Description
------------ | ------ | ------- | -----------
**vid** | - | Yes | Room code that will be updated.
**availability** | - | No | Don't send this parameter if you don't want to update availability.
**price** | - | No | Don't send this parameter if you don't want to update price.
**stop_sale** | - | No | Don't send this parameter if you don't want to update stop sale. Accepted values: `1` or `0`
**min_stay** | - | No | Don't send this parameter if you don't want to update min_stay.
**start_date** | - | Yes | Format: `YYYY-MM-DD` Start date
**end_date** | - | Yes | Format: `YYYY-MM-DD` End date
**days** | [0,1,2,3,4,5,6] | No | Used to update specific week days within given date range. (Sunday: 0)
