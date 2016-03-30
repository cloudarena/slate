# Reservations [Property]

## Get All Reservations

```shell
curl "https://app.hotelrunner.com/api/v2/apps/reservations?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
{
  "reservations": [
    {
          "hr_number": "R754208185",
          "provider_number": null,
          "channel": null,
          "state": "confirmed",
          "guest": "John Doe",
          "cancel_reason": null,
          "completed_at": "2015-01-21T10:01:25Z",
          "updated_at": "2015-01-21T09:02:51Z",
          "sub_total": 185.0,
          "extras_total": 45.0,
          "adjustments_total": 0.0,
          "tax_total": 15.0,
          "total": 245.0,
          "currency": "EUR",
          "checkin_date": "2015-01-11",
          "checkout_date": "2015-01-12",
          "note": null,
          "payment": "credit_card",
          "address": {
            "city": "istanbul",
            "state": "",
            "country": "Turkey",
            "phone": "90955223454",
            "email": "guest@example.net",
            "street": "Bagdat Cad. Istanbul",
            "street_2": null
          },
          "rooms": [
 			{
              "state": "reserved",
              "code": "HR:10105",
              "availability_group": "HR:10105",
              "price": 200.0,
			  "non_refundable": false,
              "nights": 1,
              "total_guest": 2,
              "total_adult": 2,
              "child_ages": [

              ],
              "name": "Queen Room - Disability Access - Deluxe Rate",
              "checkin_date": "2015-01-11",
              "checkout_date": "2015-01-12",
              "extra_info": "Room Extra Info:Modern bir şekilde dekore edilmiş bu stüdyoda çalışma masası ve özel banyo bulunmaktadır.\nMeal Plan:Kahvaltı oda fiyatına dahildir.\nNon-Smoking Room",
              "daily_prices": [
				{
	              "date": "2015-01-11",
	              "price": "200.0"
	            }
              ],
	          "extras": [
	            {
	              "name": "Airport Transfer (1 Person)",
	              "price": "45.0"
	            }
	          ]
            }
          ]
        }
  ],
  "count": 1,
  "current_page": 1,
  "pages": 1
}
```

This endpoint retrieves all reservations with pagination.

### HTTP Request

`GET https://app.hotelrunner.com/api/v2/apps/reservations`

### Query Parameters

Parameter | Default | Required | Description
------------ | ------ | ------- | -----------
**from_date** | 10 days before | No | Format: `YYYY-MM-DD`. If provided, reservations after this date will be retrieved.
**per_page** | 10 | No | Number of reservations per page.
**page** | 1 | No | Number of current page.
**reservation_number** | - | No | Used to get a specific reservation. It can be either HotelRunner or Channel reservation code.
**undelivered** | true | No | If set to `false`, all reservations will be shown with pagination

### Reservation Object

Name | Description
------------ | ------
**hr_number** | Reservation code on HotelRunner
**provider_number** | Reservation code on Sales Channel (can be blank*)
**channel** | Sales channel code (can be blank*)
**state** | Reservation status on HotelRunner (`reserved`,`confirmed`, `canceled`)*
**guest** | Guest name, who made the reservation
**cancel_reason** | Cancel reason (can be blank*)
**completed_at** | The time that shows when HotelRunner received the reservation (UTC)
**updated_at** | The time that shows when HotelRunner received the latest update (UTC)
**sub_total** | Sub total (tax not included)
**extras_total** | Extras total (tax not included)
**adjustments_total** | Adjustments total (Price adjustments total that made by Property Admin)
**tax_total** | Tax total
**total** | Grand total
**currency** | Currency (ISO-4217)
**checkin_date** | Check-in Date
**checkout_date** | Check-out Date
**note** | Guest note (can be blank*)
**payment** | Payment method information (`credit_card`, `bank_transfer`, `cash`, `paypal`)
**address** | See address json structure.
**rooms** > **code** | The room code.
**rooms** > **state** | The line item state in reservation. (`reserved`,`confirmed`, `canceled`)*



*blank: Empty or Null

*payment: We don't share credit card information.

*reserved: Initial state of reservation.

*confirmed: Next state of reservation when Hotelier confirms it.

