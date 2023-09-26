# WORKSHOP-Postman
WORKSHOP POSTMAN

# 1 - Install postman

```sudo dnf install snapd
sudo ln -s /var/lib/snapd/snap /snap
sudo snap install postman
```

# 2 - Open Postman

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/postman.png" width="300"/>

# 3 - Exercise

## 3.1 - Basic Request

Make a GET request on this link and get product which has id 2:
`https://dummyjson.com/products`

Expected :

```
{
    "id":2,
    "title":"iPhone X","description":"SIM-Free,
    Model A19211 6.5-inch Super Retina HD display with OLED technology A12 Bionic chip with ...","price":899,
    "discountPercentage":17.94,
    "rating":4.44,
    "stock":34,
    "brand":"Apple",
    "category":"smartphones",
    "thumbnail":"https://i.dummyjson.com/data/products/2/thumbnail.jpg",
    "images":[
        "https://i.dummyjson.com/data/products/2/1.jpg",
        "https://i.dummyjson.com/data/products/2/2.jpg",
        "https://i.dummyjson.com/data/products/2/3.jpg",
        "https://i.dummyjson.com/data/products/2/thumbnail.jpg"
    ]
}
```

## 3.2 - Discover Query Params PART 1/2

With the same Link, try to search product by phone

```
{
    "products":[{"id":1,"title":"iPhone 9",
    "description":"An apple mobile which is nothing like apple",
    "price":549,
    "discountPercentage":12.96,
    "rating":4.69,
    "stock":94,
    "brand":"Apple",
    "category":"smartphones",
    "thumbnail":"https://i.dummyjson.com/data/products/1/thumbnail.jpg",
    "images":[
        "https://i.dummyjson.com/data/products/1/1.jpg",
        "https://i.dummyjson.com/data/products/1/2.jpg",
        "https://i.dummyjson.com/data/products/1/3.jpg",
        "https://i.dummyjson.com/data/products/1/4.jpg",
        "https://i.dummyjson.com/data/products/1/thumbnail.jpg"
        ]
        }
        ,
        {
            "id":2,
            "title":"iPhone X",
            "description":"SIM-Free, Model A19211 6.5-inch Super Retina HD display with OLED technology A12 Bionic chip with ...",
            "price":899,
            "discountPercentage":17.94,
            "rating":4.44,
            "stock":34,
            "brand":"Apple",
            "category":"smartphones",
            "thumbnail":"https://i.dummyjson.com/data/products/2/thumbnail.jpg"
            ,"images":[
                "https://i.dummyjson.com/data/products/2/1.jpg",
                "https://i.dummyjson.com/data/products/2/2.jpg",
                "https://i.dummyjson.com/data/products/2/3.jpg",
                "https://i.dummyjson.com/data/products/2/thumbnail.jpg"
            ]
        },
        {
            "id":71,
            "title":"Women Shoulder Bags","description":
            "LouisWill Women Shoulder Bags Long Clutches Cross Body Bags Phone Bags PU Leather Hand Bags Large Capacity Card Holders Zipper Coin Purses Fashion Crossbody Bags for Girls Ladies",
            "price":46,
            "discountPercentage":14.65,
            "rating":4.71,"stock":17,
            "brand":"LouisWill",
            "category":"womens-bags",
            "thumbnail":"https://i.dummyjson.com/data/products/71/thumbnail.jpg",
            "images":[
                "https://i.dummyjson.com/data/products/71/1.jpg",
                "https://i.dummyjson.com/data/products/71/2.jpg",
                "https://i.dummyjson.com/data/products/71/3.webp",
                "https://i.dummyjson.com/data/products/71/thumbnail.jpg"
                ]
            },
            {
                "id":86,
                "title":"Bluetooth Aux",
                "description":"Bluetooth Aux Bluetooth Car Aux Car Bluetooth Transmitter Aux Audio Receiver Handfree Car Bluetooth Music Receiver Universal 3.5mm Streaming A2DP Wireless Auto AUX Audio Adapter With Mic For Phone MP3",
                "price":25,
                "discountPercentage":10.56,
                "rating":4.57,
                "stock":22,
                "brand":"Car Aux",
                "category":"automotive",
                "thumbnail":"https://i.dummyjson.com/data/products/86/thumbnail.jpg",
                "images":[
                    "https://i.dummyjson.com/data/products/86/1.jpg",
                    "https://i.dummyjson.com/data/products/86/2.webp",
                    "https://i.dummyjson.com/data/products/86/3.jpg",
                    "https://i.dummyjson.com/data/products/86/4.jpg",
                    "https://i.dummyjson.com/data/products/86/thumbnail.jpg"
                ]
            }
            ],"total":4,"skip":0,"limit":4}
```


## 3.2.1 - Discover Query Params PART 2/2

It's a very long response, why not trying to juste display the first occurence ? Try to use limit.
Your outpout should seems like that:

```
{
    "products":[
        {
            "id":1,
            "title":"iPhone 9",
            "description":"An apple mobile which is nothing like apple",
            "price":549,
            "discountPercentage":12.96,
            "rating":4.69,
            "stock":94,
            "brand":"Apple",
            "category":"smartphones",
            "thumbnail":"https://i.dummyjson.com/data/products/1/thumbnail.jpg",
            "images":[
                "https://i.dummyjson.com/data/products/1/1.jpg",
                "https://i.dummyjson.com/data/products/1/2.jpg",
                "https://i.dummyjson.com/data/products/1/3.jpg",
                "https://i.dummyjson.com/data/products/1/4.jpg",
                "https://i.dummyjson.com/data/products/1/thumbnail.jpg"
                ]
        }
    ],
    "total":4,
    "skip":0,
    "limit":1
}
```

## 3.3 - Try your first POST request

`https://dummyjson.com/products/add`

On this link, try to add a product with the title: "BMW Pencil"
The request must return a message in JSON format :

```
{
    "id": 101,
    "title": "BMW Pencil"
}
```

## 3.4 - Try your first PUT request

`https://dummyjson.com/products/`
Now, try to update the product which have id one, with title: "iPhone Galaxy +1". You should see this outpout :

```
{
    "id": 1,
    "title": "iPhone Galaxy +1",
    "price": 549,
    "stock": 94,
    "rating": 4.69,
    "images": [
        "https://i.dummyjson.com/data/products/1/1.jpg",
        "https://i.dummyjson.com/data/products/1/2.jpg",
        "https://i.dummyjson.com/data/products/1/3.jpg",
        "https://i.dummyjson.com/data/products/1/4.jpg",
        "https://i.dummyjson.com/data/products/1/thumbnail.jpg"
    ],
    "thumbnail": "https://i.dummyjson.com/data/products/1/thumbnail.jpg",
    "description": "An apple mobile which is nothing like apple",
    "brand": "Apple",
    "category": "smartphones"
}
```

## 3.5 - Try your DELETE request

Finaly, try to delete the object with the id one on the same link than before. You should see this outpout :

```
{
    "id": 1,
    "title": "iPhone 9",
    "description": "An apple mobile which is nothing like apple",
    "price": 549,
    "discountPercentage": 12.96,
    "rating": 4.69,
    "stock": 94,
    "brand": "Apple",
    "category": "smartphones",
    "thumbnail": "https://i.dummyjson.com/data/products/1/thumbnail.jpg",
    "images": [
        "https://i.dummyjson.com/data/products/1/1.jpg",
        "https://i.dummyjson.com/data/products/1/2.jpg",
        "https://i.dummyjson.com/data/products/1/3.jpg",
        "https://i.dummyjson.com/data/products/1/4.jpg",
        "https://i.dummyjson.com/data/products/1/thumbnail.jpg"
    ],
    "isDeleted": true,
    "deletedOn": "2023-02-27T16:53:17.285Z"
}
```

## 3.6 - Try your GET request

Now, try to make a GET request on this link :
And get information for the product with id 2

`https://dummyjson.com/products/2`


```
{
    "id":2,
    "title":"iPhone X",
    "description":"SIM-Free, Model A19211 6.5-inch Super Retina HD display with OLED technology A12 Bionic chip with ...",
    "price":899,
    "discountPercentage":17.94,
    "rating":4.44,
    "stock":34,
    "brand":"Apple",
    "category":"smartphones",
    "thumbnail":"https://i.dummyjson.com/data/products/2/thumbnail.jpg"
    ,"images":[
        "https://i.dummyjson.com/data/products/2/1.jpg",
        "https://i.dummyjson.com/data/products/2/2.jpg",
        "https://i.dummyjson.com/data/products/2/3.jpg",
        "https://i.dummyjson.com/data/products/2/thumbnail.jpg"
    ]
},
```

# 3.7 - Try your first request with a variable

Now, try to create a variable with the name `id` and the value `1`. Then, try to make a GET request on this link.

You should see the same outpout than before.


# Final step :

Now try to create an API to and implement all the previous route. You're free to use all languages like Python, JavaScript etc...

# Unit Tests

## Create a collection

Now you have create your own server. You should setup some unit - test. With Postman you can do some.
To do so, go to
`collection :`

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/collection.png" width="200"/>

Then, create a new collection :

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/New.png" width="200"/>

Fill all fields like you have seen before (urls etc...)

## Set up Units tests

Go to `Test` Tab :

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/Tests.png" width="200"/>

Check on the right some tests example :

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/Example.png" width="200"/>

Now, make some unit test for all routes you have create.

- Your routes should always response a 200 sucess code
- The reponse time should be < 400ms
- You should verify the content of the response

Finally, you should have 3 - 5 tests for every routes.

Here some outputs example :

<img src="https://github.com/kvn703/WORKSHOP-Postman/blob/main/TestsResults.png" width="500"/>

Of course, all tests MUST BE in PASS status and none should fail.

# FINALLY

**Find how to EXPORT your Collection and send us via mail to check your tests**

`kevin.nadarajah@epitech.eu` or `anatole.babin@epitech.eu`

GOOD LUCK !