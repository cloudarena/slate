# Rooms [Property]

## Get Room List

```shell
curl "https://app.hotelrunner.com/api/v1/apps/rooms?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
[

  {
    "code": "HR:1",
    "availability_group": "HR:1",
    "availability_update": true,
    "restrictions_update": true,
    "price_update": true,
    "name": "Standard Room",
    "description": "Standard Room Description",
    "policy": "Standard Room Policy",
    "room_capacity": 3,
    "adult_capacity": 2,
    "channel_codes": ["bookingcom", "online", "hrs", "expedia"]
  },
  {
    "code": "NR:HR:1",
    "availability_group": "HR:1",
    "availability_update": false,
    "restrictions_update": false,
    "price_update": false,
    "name": "Standard Room - NR",
    "description": "Standard Room Description",
    "policy": "Standard Room Policy",
    "room_capacity": 3,
    "adult_capacity": 2,
    "channel_codes": ["bookingcom", "online", "hrs", "expedia"]
  },
  {
    "code": "HR:2",
    "availability_group": "HR:2",
    "availability_update": true,
    "restrictions_update": true,
    "price_update": true,
    "name": "Double Room",
    "description": "Double Room Description",
    "policy": "Double Room Policy",
    "room_capacity": 2,
    "adult_capacity": 2,
    "channel_codes": ["bookingcom", "online", "hrs"]
  }
]
```

This endpoint retrieves all rooms of property.

### HTTP Request

`GET https://app.hotelrunner.com/api/v1/apps/rooms`

### Room Object

Name | Description
------------ | ------
**code** | Room code on HotelRunner (`NR` means Non refundable)
**availability_group** | Room availability group on HotelRunner. All availabilities of rates are same within same group.  
**availability_update** | Only room whose `availability_update``=`true` can update availabilities.  
**restrictions_update** | Only room whose `restrictions_update``=`true` can update restrictions.  
**price_update** | Only room whose `price_update``=`true` can update prices.  
**name** | Name of room
**description** | Description of room
**policy** | Free text policy for room
**room_capacity** | Maximum room capacity including children
**adult_capacity** | Maximum adult count that can stay in room
**channel_codes** | Channel codes of which room is connected with


## Update Room


```shell
curl -X PUT --data "hr_id={HR_ID}&token={TOKEN}&room_code={ROOM_CODE}&channel_codes[]={CHANNEL_CODE_1}&channel_codes[]={CHANNEL_CODE_2}&start_date={START_DATE}&end_date={END_DATE}&availability={AVAILABILITY}&price={PRICE}&min_stay={MIN_STAY}&stop_sale={STOP_SALE}" https://app.hotelrunner.com/api/v1/apps/rooms/~
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
**room_code** | - | Yes | Room code that will be updated.
**availability** | - | No | Don't send this parameter if you don't want to update availability.
**price** | - | No | Don't send this parameter if you don't want to update price.
**stop_sale** | - | No | Don't send this parameter if you don't want to update stop sale. Accepted values: `1` or `0`
**cta** | - | No | Don't send this parameter if you don't want to update CTA. Accepted values: `1` or `0`
**ctd** | - | No | Don't send this parameter if you don't want to update CTD. Accepted values: `1` or `0`
**min_stay** | - | No | Don't send this parameter if you don't want to update min_stay.
**start_date** | - | Yes | Format: `YYYY-MM-DD` Start date
**end_date** | - | Yes | Format: `YYYY-MM-DD` End date
**days** | [0,1,2,3,4,5,6] | No | Type: `Array` Used to update specific week days within given date range. (Sunday: 0)
**channel_codes** | All connected channels of room | No | Type: `Array` Used to update specific channels. (eg. ['bookingcom', 'online'])
