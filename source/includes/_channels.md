# Rooms (Property)

## Get HotelRunner Channel List

```shell
curl "https://app.hotelrunner.com/api/v1/apps/infos/channels?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
[

    {
      "name": "Booking.com",
      "code": "bookingcom"
    },

    {
      "name": "HRS",
      "code": "hrs"
    },
    {
      "name": "Expedia Inc.",
      "code": "expedia"
    }
]
```

This endpoint retrieves all available channels of HotelRunner.

### HTTP Request

`GET https://app.hotelrunner.com/api/v1/apps/infos/channels`

### Channel Object

Name | Description
------------ | ------
**name** | Channel name
**code** | Channel code. (This code will be used on Room calendar updates.)

## Get Connected Channel List of a Property


```shell
curl "https://app.hotelrunner.com/api/v1/apps/infos/connected_channels?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
[

   {
       "name": "Online",
       "code": "online",
       "in_progress": 0,
       "succeeded": 0,
       "failed": 0
     },
     {
       "name": "Booking.com",
       "code": "bookingcom",
       "in_progress": 132,
       "succeeded": 297,
       "failed": 0
     }
]
```

This endpoint retrieves all connected channels of a Property with process stats.

### HTTP Request

`GET https://app.hotelrunner.com/api/v1/apps/infos/connected_channels`

### Property Channel Object

Name | Description
------------ | ------
**name** | Channel name
**code** | Channel code. (This code will be used on Room calendar updates.)
**in_progress** | Total process count that are being processed.
**succeeded** | Total process count that were successfully updated.
**failed** | Total process count that were failed.
