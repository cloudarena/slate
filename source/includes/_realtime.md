# Real-time

## Real-time Push Reservation

> The POST you will see coming will look like this:

```shell
"https://yourdomain.com/callback?token={TOKEN}&hr_id={HR_ID}&data={JSON_RESERVATION_DATA}"
```

> The above url includes JSON data structured like this:

```json
{
      "hr_number": "R754208185",
      "provider_number": "32423234422",
      "channel": "Booking.com",
      "state": "confirmed",
      "guest": "John Doe",
      "cancel_reason": null,
      "completed_at": "2015-01-21T10:01:25Z",
      "updated_at": "2015-01-21T09:02:51Z",
      "sub_total": 370.0,
      "extras_total": 0.0,
      "adjustments_total": 0.0,
      "tax_total": 30.0,
      "total": 400.0,
      "currency": "EUR",
      "checkin_date": "2015-01-11",
      "checkout_date": "2015-01-12",
      "note": null,
      "payment": "credit_card",
      "address": {
        "city": "Istanbul",
        "state": "",
        "country": "Turkey",
        "phone": "90955223454",
        "email": "guest@example.net",
        "street": "Bagdat Cad. Istanbul",
        "street_2": null
      },
      "rooms": {
        "15571": {
          "state": "reserved",
          "code": "HR:10105",
          "price": 200.0,
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
              "price": "100.0"
            }
          ],
          "extras": [

          ]
        },
        "15572": {
          "state": "reserved",
          "code": "HR:10105",
          "price": 200.0,
          "nights": 1,
          "total_guest": 2,
          "total_adult": 2,
          "child_ages": [

          ],
          "name": "Single Room - Non Refundable Rate",
          "checkin_date": "2015-01-11",
          "checkout_date": "2015-01-12",
          "extra_info": "Room Extra Info:Modern bir şekilde dekore edilmiş bu stüdyoda çalışma masası ve özel banyo bulunmaktadır.\nMeal Plan:Kahvaltı oda fiyatına dahildir.\nNon-Smoking Room",
          "daily_prices": [
            {
              "date": "2015-01-11",
              "price": "100.0"
            }
          ],
          "extras": [

          ]
        }
      }
    }

```

Real-time push reservations provide your application with instant notifications of new/updated reservations as
they are received by HotelRunner.

### Create a Callback URL

When we have new updates to send your server, we do a simple POST with a payload containing updates to a URL on your server.
This callback URL must be HTTPS and support POST method.

`https://yourdomain.com/callback`

For instance, the POST you will see coming will look like this:

`https://yourdomain.com/callback?token={TOKEN}&hr_id={HR_ID}&data={JSON_RESERVATION_DATA}`


### Reservation Object

Name | Description
------------ | ------
**hr_number** | Reservation code on HotelRunner
**provider_number** | Reservation code on Sales Channel (can be blank*)
**channel** | Sales channel name (can be blank*)
**state** | Reservation status on HotelRunner (`confirmed`, `canceled`, `complete`)
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
**rooms** > **state** | The line item state in reservation. (`confirmed`, `canceled`, `reserved`)



*blank: Empty or Null
