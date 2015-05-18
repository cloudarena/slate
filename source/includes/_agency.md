<!-- This section removed from first navbar with toc-ignore.This section added with manualy to second navbar -->

## Search [Agency]

```shell
curl "http://api-test-agency.hotelrunner.com/api/affiliate_stores/search"
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
         "name":"ilkayorhanlar-property6",
         "code":"ilkayorhanlar-property6",
         "url":"http://ilkayorhanlar.otamagic.com:3002/property/ilkayorhanlar-property6",
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

GET http://api-test-agency.hotelrunner.com/api/affiliate_stores/search

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
token | - | Yes | About security access
property_name | - | Yes | -
location | - | Yes | -

## Auto complete [Agency]

```shell
curl "http://api-test-agency.hotelrunner.com/api/affiliate_stores/auto-complete"
```

> The above command returns JSON structured like this:

```json
{  
   "results":{  
      "properties":[  
         {  
            "code":"ilkayorhanlar-property5",
            "name":"ilkayorhanlar-property5"
         },
         {  
            "code":"ilkayorhanlar-property6",
            "name":"ilkayorhanlar-property6"
         }
      ],
      "addresses":[  

      ]
   }
}
```
This endpoint retrieves available properties and addresses.(Only code and name of about object)

### HTTP REQUEST

GET http://api-test-agency.hotelrunner.com/api/affiliate_stores/auto-complete

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
token     |    -    |    Yes   | About security access
property_name   | - |       Yes  | This is used as keyword to search properties

## Detail [Agency]

```shell
curl "http://api-test-agency.hotelrunner.com/api/affiliate_stores/detail"
```

> The above command returns JSON structured like this:

```json
{  
   "property":{  
      "address":"Bakırköy, Istanbul",
      "latitude":"40.978",
      "longitude":"28.86959999999999",
      "canonical_address":"Ataköy 1 Mh., Fişekhane Cd 4-56, 34140 Bakırköy/İstanbul, Turkey",
      "name":"ilkayorhanlar-property6",
      "code":"ilkayorhanlar-property6",
      "url":"http://ilkayorhanlar.otamagic.com:3002/property/ilkayorhanlar-property6",
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
            "url":"/spree/products/original/a9aea63c-672a-4f19-a23c-310f5e4b197d.jpg",
            "alt":null
         },
         {  
            "url":"/spree/products/original/3d0f2278-dbd0-4742-b955-97aedb50290d.jpg",
            "alt":null
         }
      ],
      "room_types":[  
         {  
            "images":[  
               {  
                  "url":"/spree/products/large/74051365-fc65-4590-ade3-b42c774187e8.jpg",
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
                  "url":"/spree/products/large/b234593f-f49b-4071-bd19-65ee545dbff9.jpg",
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

GET http://api-test-agency.hotelrunner.com/api/affiliate_stores/detail

### QUERY PARAMETERS

Parameter | Default | Required | Description
--------- | ------- | ---------|-----------
token     |    -    |    Yes   | About security access
property_code   | - |       Yes  | To access property detail





