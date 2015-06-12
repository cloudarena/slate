<!-- This section removed from first navbar with toc-ignore.This section added with manualy to second navbar -->

# Properties [Agency]

## Fetch [Agency]

```shell
curl "https://app.hotelrunner.com/api/v1/apps/agency/properties/fetch?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
{
   "properties":[
      {
         "address":"Bakırköy, Istanbul",
         "latitude":"40.978",
         "longitude":"28.86959999999999",
         "canonical_address":"Ataköy 1 Mh., Fişekhane Cd 4-56, 34140 Bakırköy/İstanbul, Turkey",
         "name":"agency-property1",
         "code":"agency-property",
         "url":"https://app.hotelrunner.com/property/agency-property1",
         "currency":"TRY",
         "overview":null,
         "image_url":"noimage",
         "from_price":1.0,
         "price_available":true
      }
   ],
   "count":1,
   "current_page":1,
   "pages":1
}
```
This endpoint retrieves available properties with pagination.

### HTTP REQUEST

GET https://app.hotelrunner.com/api/v1/apps/agency/properties/fetch

## Search [Agency]

```shell
curl "https://app.hotelrunner.com/api/v1/apps/agency/properties/search?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
{  
   "search_results":[  
      {  
         "address":"Bakırköy, Istanbul",
         "latitude":"40.978",
         "longitude":"28.86959999999999",
         "canonical_address":"Ataköy 1 Mh., Fişekhane Cd 4-56, 34140 Bakırköy/İstanbul, Turkey",
         "name":"agency-property1",
         "code":"agency-property",
         "url":"https://app.hotelrunner.com/property/agency-property1",
         "currency":"TRY",
         "overview":null,
         "image_url":"noimage",
         "from_price":1.0,
         "price_available":true
      }
   ],
   "count":1,
   "current_page":1,
   "pages":1
}
```
This endpoint retrieves available properties with pagination by given parameters.

### HTTP REQUEST

GET https://app.hotelrunner.com/api/v1/apps/agency/properties/search

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
property_name | - | No | -
location | - | Yes | -

## Auto complete [Agency]

```shell
curl "https://app.hotelrunner.com/api/v1/apps/agency/properties/auto_complete?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
{  
   "results":{  
      "properties":[  
         {  
            "code":"agency-property1",
            "name":"agency-property1"
         },
         {  
            "code":"agency-property2",
            "name":"agency-property2"
         }
      ],
      "addresses":[  

      ]
   }
}
```
This endpoint retrieves available properties and addresses.(Only code and name of about object)

### HTTP REQUEST

GET https://app.hotelrunner.com/api/v1/apps/agency/properties/auto_complete

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
property_name   | - |       Yes  | This is used as keyword to search properties

## Detail [Agency]

```shell
curl "https://app.hotelrunner.com/api/v1/apps/agency/properties/detail?token={TOKEN}&hr_id={HR_ID}"
```

> The above command returns JSON structured like this:

```json
{  
   "property":{  
      "address":"Bakırköy, Istanbul",
      "latitude":"40.978",
      "longitude":"28.86959999999999",
      "canonical_address":"Ataköy 1 Mh., Fişekhane Cd 4-56, 34140 Bakırköy/İstanbul, Turkey",
      "name":"agency-property1",
      "code":"agency-property1",
      "url":"https://app.hotelrunner.com/property/agency-property1",
      "currency":"TRY",
      "overview":null,
      "from_price":1.0,
      "price_available":true,
      "services":"[]",
      "facilities":"[]",
      "policies":[  
         {  
            "checkin_policy":"After 15:00 day of arrival."
         },
         {  
            "checkout_policy":"11:00 upon day of departure."
         },
         {  
            "smoking_policy":"Smoking is allowed."
         },
         {  
            "pets_policy":"No pets allowed"
         }
      ],
      "images":[  
         {  
            "url":"http://cdn-cms1.hotelrunner.com/assets/photos/original/f46abbff-9693-4586-a463-770ccd998b20.jpg",
            "alt":null
         },
         {  
            "url":"http://cdn-cms1.hotelrunner.com/assets/photos/original/f46abbff-9693-4586-a463-770ccd998b21.jpg",
            "alt":null
         }
      ],
      "room_types":[  
         {  
            "images":[  
               {  
                  "url":"http://cdn-cms2.hotelrunner.com/assets/photos/large/97eeffe8-a1c8-4753-bf35-dcd15d0b5c09.jpg",
                  "alt":null
               }
            ],
            "name":"Apartment ",
            "bed_types":"Twin Extra Long",
            "description":"Twin Extra Long"
         },
         {  
            "images":[  
               {  
                  "url":"http://cdn-cms2.hotelrunner.com/assets/photos/large/97eeffe8-a1c8-4753-bf35-dcd15d0b5c11.jpg",
                  "alt":null
               }
            ],
            "name":"Balayı Odası 1 ",
            "bed_types":"Queen and California/Western king",
            "description":"Balayı Odası 1"
         }
      ]
   }
}
```
This endpoint retrieves available property (Includes extra details of property like images, room_types, etc)

### HTTP REQUEST

GET https://app.hotelrunner.com/api/v1/apps/agency/properties/detail

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
property_code   | - |       Yes  | To access property detail





