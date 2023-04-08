# Product #

The products API allows you to retrieve product details and product description.

## Fetch a product ##

This API helps you to retrieve product details by link.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/customer/external/fetch-product</h6>
	</div>
</div>


> Example of retrieving product details:

```shell
curl -X POST BASE_URL/api/v1/customer/external/fetch-product \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json" \
	-d '{
    "url": "https://www.aliexpress.com/item/1005002952248539.html"
}'
```


> JSON response example:

```json
{
  "status": "success",
  "code": 200,
  "message": "Product has been fetched.",
  "data": {
    "id": 4408374,
    "shop_id": 1,
    "vid": "1005002952248539",
    "seller_id": 522242,
    "vendor": "aliexpress",
    "title": "XIAOMI Mijia Handheld Garment Steamer for Clothes Electric Steam Iron High Quality Portable Traveling Clothes Steamer",
    "description": null,
    "price": {
      "discount": {
        "max": 43.63,
        "min": 25.99
      },
      "original": {
        "max": 54.54,
        "min": 32.49
      }
    },
    "stock": 1207,
    "sales": 6079,
    "link": "https://www.aliexpress.com/item/1005002952248539.html",
    "image": "https://ae01.alicdn.com/kf/Hedb73ff2ad254ba3b0d27ae6d6a5a6455/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
    "meta": {
      "vendor": "aliexpress",
      "companyId": 249292525,
      "categoryId": 64904,
      "product_id": "1005002952248539",
      "description_url": "https://aeproductsourcesite.alicdn.com/product/description/pc/v2/en_US/desc.htm?productId=1005002952248539&key=S9c91991033774b91b571e31c48528658I.zip&token=757b28f8463f826b8108399a160a7e22"
    },
    "gallery": [
      {
        "url": "https://ae01.alicdn.com/kf/Hedb73ff2ad254ba3b0d27ae6d6a5a6455/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/Hedb73ff2ad254ba3b0d27ae6d6a5a6455/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      },
      {
        "url": "https://ae01.alicdn.com/kf/H44c1d4eb0b3044bfaad4da560861fbed2/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/H44c1d4eb0b3044bfaad4da560861fbed2/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      },
      {
        "url": "https://ae01.alicdn.com/kf/H386b4cfa0b7b43479fd22ec851a4d8c1P/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/H386b4cfa0b7b43479fd22ec851a4d8c1P/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      },
      {
        "url": "https://ae01.alicdn.com/kf/Hadf8bc907c8349d0be7b46041b54df923/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/Hadf8bc907c8349d0be7b46041b54df923/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      },
      {
        "url": "https://ae01.alicdn.com/kf/H276830446dc341658d597a72e1b2ac0d7/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/H276830446dc341658d597a72e1b2ac0d7/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      },
      {
        "url": "https://ae01.alicdn.com/kf/U0c688e4f6be442f3aa09de2752a42a7ff/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg",
        "thumb": "https://ae01.alicdn.com/kf/U0c688e4f6be442f3aa09de2752a42a7ff/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
        "title": null
      }
    ],
    "ratings": [
      25,
      10,
      17,
      71,
      1381
    ],
    "ratings_count": 1504,
    "ratings_average": "4.80",
    "variation": {
      "skus": [
        {
          "id": 12000026289211983,
          "price": {
            "offer": 43.63,
            "actual": 54.54,
            "preorder": null
          },
          "props": "29,201336100,200660849",
          "stock": {
            "min": null,
            "limit": 0,
            "available": 443
          }
        },
        {
          "id": 12000026289211984,
          "price": {
            "offer": 43.63,
            "actual": 54.54,
            "preorder": null
          },
          "props": "29,201336100,200660850",
          "stock": {
            "min": null,
            "limit": 0,
            "available": 764
          }
        },
        {
          "id": 12000026289211985,
          "price": {
            "offer": 28.82,
            "actual": 36.03,
            "preorder": null
          },
          "props": "29,201336103,200660849",
          "stock": {
            "min": null,
            "limit": 0,
            "available": 0
          }
        },
        {
          "id": 12000026289211986,
          "price": {
            "offer": 25.99,
            "actual": 32.49,
            "preorder": null
          },
          "props": "29,201336103,200660850",
          "stock": {
            "min": null,
            "limit": 0,
            "available": 0
          }
        }
      ],
      "props": [
        {
          "id": 14,
          "name": "Color",
          "values": [
            {
              "id": 29,
              "name": "White",
              "color": "#FFFFFF",
              "image": "https://ae01.alicdn.com/kf/Hb4b4737007a64698bac131828e08bc0aw/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_640x640.jpg",
              "thumb": "https://ae01.alicdn.com/kf/Hb4b4737007a64698bac131828e08bc0aw/XIAOMI-Mijia-Handheld-Garment-Steamer-for-Clothes-Electric-Steam-Iron-High-Quality-Portable-Traveling-Clothes-Steamer.jpg_50x50.jpg",
              "title": "White"
            }
          ]
        },
        {
          "id": 200007763,
          "name": "Ships From",
          "values": [
            {
              "id": 201336100,
              "name": "China",
              "color": null,
              "image": null,
              "thumb": null,
              "title": "China"
            },
            {
              "id": 201336103,
              "name": "Russian Federation",
              "color": null,
              "image": null,
              "thumb": null,
              "title": "Russian Federation"
            }
          ]
        },
        {
          "id": 200009209,
          "name": "Plug Type",
          "values": [
            {
              "id": 200660849,
              "name": "US",
              "color": null,
              "image": null,
              "thumb": null,
              "title": "US"
            },
            {
              "id": 200660850,
              "name": "EU",
              "color": null,
              "image": null,
              "thumb": null,
              "title": "EU"
            }
          ]
        }
      ]
    },
    "created_at": "2022-11-21T09:27:38.000000Z",
    "updated_at": "2022-11-22T03:06:57.000000Z",
    "shop": {
      "id": 1,
      "name": "AliExpress",
      "url": "https://www.aliexpress.com",
      "identifier": "aliexpress",
      "country_code": "CN",
      "currency_code": "USD",
      "currency_symbol": "$",
      "fx": "90.00"
    },
    "seller": {
      "id": 522242,
      "name": "Mi Eco-chain Store",
      "vendor": "aliexpress",
      "vendor_id": "1101489720",
      "link": "https://www.aliexpress.com/store/1101489720",
      "description": null,
      "meta": {
        "trusted": "97.3%",
        "toprated": true,
        "admin_seq": 241649285,
        "followers": 20841,
        "positives": 7589
      },
      "opened_at": "2020-04-16T00:00:00.000000Z"
    },
    "categories": [],
    "specifications": [
      {
        "label": {
          "id": 12,
          "name": "Model Number"
        },
        "value": {
          "id": 6261154,
          "name": "XIAOMI Mijia steaming iron"
        }
      },
      {
        "label": {
          "id": 13,
          "name": "Brand Name"
        },
        "value": {
          "id": 1401526,
          "name": "XIAOMI"
        }
      },
      {
        "label": {
          "id": 20,
          "name": "Feature"
        },
        "value": {
          "id": 6261156,
          "name": "handheld garment steamer iron"
        }
      },
      {
        "label": {
          "id": 24,
          "name": "Support"
        },
        "value": {
          "id": 1382444,
          "name": "Yes"
        }
      },
      {
        "label": {
          "id": 439,
          "name": "Voltage (V)"
        },
        "value": {
          "id": 1391,
          "name": "220V"
        }
      },
      {
        "label": {
          "id": 3158,
          "name": "Temperature Gear"
        },
        "value": {
          "id": 413207,
          "name": "Two tranches thermostat"
        }
      },
      {
        "label": {
          "id": 3159,
          "name": "Water Tank Capacity (l)"
        },
        "value": {
          "id": 10076,
          "name": "<0.8L"
        }
      },
      {
        "label": {
          "id": 3160,
          "name": "Supports Anti Dry Burning"
        },
        "value": {
          "id": 1382444,
          "name": "Yes"
        }
      },
      {
        "label": {
          "id": 6190,
          "name": "Steam Duration (Min)"
        },
        "value": {
          "id": 133846,
          "name": "60min"
        }
      },
      {
        "label": {
          "id": 212542,
          "name": "Certification"
        },
        "value": {
          "id": 521424,
          "name": "CE"
        }
      },
      {
        "label": {
          "id": 212560,
          "name": "color"
        },
        "value": {
          "id": 6261155,
          "name": "white color garment steamer"
        }
      },
      {
        "label": {
          "id": 212643,
          "name": "Classification"
        },
        "value": {
          "id": 1404611,
          "name": "Steam brush"
        }
      },
      {
        "label": {
          "id": 212735,
          "name": "Plug Type"
        },
        "value": {
          "id": 6261157,
          "name": "China Plug Type with different adaptor"
        }
      },
      {
        "label": {
          "id": 212824,
          "name": "Origin"
        },
        "value": {
          "id": 1381952,
          "name": "Mainland China"
        }
      },
      {
        "label": {
          "id": 214519,
          "name": "Power (W)"
        },
        "value": {
          "id": 472504,
          "name": "1200W"
        }
      }
    ]
  }
}
```

## Fetch extended description of a product  ##

This API helps you to retrieve extended description for a product by link.

### HTTP request ###

<div class="api-endpoint">
	<div class="endpoint-data">
		<i class="label label-post">POST</i>
		<h6>/customer/fetch-product-description</h6>
	</div>
</div>


> Example of retrieving extended description of product:

```shell
curl -X POST BASE_URL/api/v1/customer/fetch-product-description \
	-H "Authorization: Bearer %token%" \
	-H "Content-Type: application/json" \
	-d '{
    "url": "https://detail.1688.com/offer/675196975564.html",
    "type": "body"
}'
```


> JSON response example:

```json
{
  "data": "<div id=\"offer-template-0\"></div><p><span style=\"color: #942828;\"><strong><span style=\"font-size: 16.0pt;font-family: simsun;\"><img src=\"https://cbu01.alicdn.com/img/ibank/O1CN01WCRyeS2N9s4dgI3s5_!!978309921-0-cib.jpg?__r__=1631584793830\" alt=\"111.jpg\" width=\"790\" height=\"136.20689655172416\"><br class=\"img-brk\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/O1CN01m0tfy82N9s4iSITig_!!978309921-0-cib.jpg?__r__=1631584793831\" alt=\"2222.jpg\" width=\"790\" height=\"129.19791666666666\"><br class=\"img-brk\"><br class=\"img-brk\"><span style=\"color: #000000;\">Various customers and dealers are welcome to wholesale goods to make the same. According to customer requirements, the laser LOGO can be supported, supporting the sample, and supporting a generation. Large customers can directly dial the contact phone number to get preferential prices! If you have any questions on any product, you can also consult the customer service. Xiao Chen Qian religiously answered you.</span></span></strong></span></p><p><img src=\"https://cbu01.alicdn.com/img/ibank/2020/245/674/18657476542_323357090.jpg?__r__=1652520135198\" alt=\"WeChat picture_20200605143714.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/255/689/18581986552_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605143741.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/956/299/18581992659_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605222610.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/410/552/18519255014_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605143810.jpg\"></p><p><img src=\"https://cbu01.alicdn.com/img/ibank/2020/113/400/18582004311_323357090.jpg?__r__=1652520207795\" alt=\"WeChat picture_20200605143813.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/217/089/18581980712_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605143744.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/412/042/18519240214_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605143746.jpg\"><br class=\"img-brk\"><img src=\"https://cbu01.alicdn.com/img/ibank/2020/890/942/18519249098_323357090.jpg?__r__=1652520135199\" alt=\"WeChat picture_20200605143750.jpg\"><br class=\"img-brk\"><br class=\"img-brk\"></p><p><span style=\"color: #993300;\"><strong><span style=\"font-size: 16.0pt;font-family: simsun;\"><span style=\"font-size: 24.0pt;background-color: #808080;\"><span style=\"color: #000000;\">丨 Company profile/main product 丨（Company/main Products）</span></span><br><img src=\"https://cbu01.alicdn.com/img/ibank/O1CN01OZkj832N9s9iMiZtv_!!978309921-0-cib.jpg?__r__=1666582939646\" alt=\"Factor map\"><br class=\"img-brk\"><span style=\"font-size: 24.0pt;background-color: #808080;color: #000000;\">exhibition site</span><br><img src=\"https://cbu01.alicdn.com/img/ibank/2020/431/344/13726443134_323357090.jpg\" alt=\"undefined\" width=\"790\" height=\"443.96354166666663\"><br><img src=\"https://cbu01.alicdn.com/img/ibank/2020/558/095/13763590855_323357090.jpg\" alt=\"undefined\"><br><br><img src=\"https://cbu01.alicdn.com/img/ibank/2020/417/347/13809743714_323357090.jpg\" alt=\"undefined\" width=\"790\" height=\"180.91603053435114\"><br><span style=\"font-size: 24.0pt;\"><span style=\"background-color: #808080;\"></span><span style=\"background-color: #808080;\"><span style=\"color: #000000;\">Tips</span></span></span><br></span></strong></span></p><p><span style=\"color: #000000;\"><strong><span style=\"font-size: 15.0pt;\">Do not rush to use after getting the kitchen utensils. First clean it with vinegar or neutral cleaner to remove the residual polished wax in the manufacturing and the imprints left after contacting the product in the packaging and handling. Essence The products are shot in kind. Due to the factors of photography technology, lighting and display color rendering, the color or size of the picture may have some errors with the real object.</span></strong></span></p><p></p><p><span style=\"font-size: 24.0pt;background-color: #808080;\">Question answer</span></p><p></p><div><span style=\"background-color: #999999;font-size: 16.0pt;\">One: Are we factories?</span></div><p></p><p><span style=\"font-size: 12.0pt;\">Answer: We are a professional stainless steel tableware and stainless steel kitchenware manufacturers integrating product research and development, manufacturing and sales, and are located in Jieyang, known as the \"China Hardware Base\".</span></p><p></p><div><div><span style=\"font-size: 16.0pt;background-color: #999999;\">Two: Can the product be customized?</span></div><div><span style=\"font-size: 12.0pt;\">Answer: Yes, all our products can be customized, including printing words on cloth bags, printing words on the carton, laser engraving on the product, and custom -customized logo costs. Please consult customer service for specific costs.</span></div><div></div><div><span style=\"font-size: 16.0pt;background-color: #999999;\">Three: Is there a spot in the product?</span></div><div><span style=\"font-size: 12.0pt;\">Answer: 98%of the pages can be taken in stock. If the logo is not customized, it can be shipped within 72 hours. If the phenomenon of shortcoming after placing an order, we will inform you within 24 hours after your payment.</span></div><div></div><span style=\"font-size: 16.0pt;background-color: #999999;\">Four: How is the freight calculated?</span><p><span style=\"font-size: 12.0pt;\">Answer: Dear customers, after taking the order, please contact the customer service to inform the logistics you need to ship and confirm your order information to avoid delaying your precious time. If the shipping station is needed, we will send you the logistics you specified to the payment（The logistics company calculates the freight according to the actual weight volume.）Essence If you need to send a courier, we will account for the freight before you pay, so that you will pay for you! A small amount of samples or goods is generally sent through express delivery.</span></p><p></p><p><span style=\"background-color: #999999;font-size: 16.0pt;\">Four: Is the product environmentally friendly?</span></p></div><p></p><p><span style=\"font-size: 12.0pt;\">Answer: Our products use high -quality and environmentally friendly new stainless steel materials. It is non -toxic and heavy metal, which is environmentally friendly.</span></p><p></p><p><span style=\"color: #993300;\"><strong><span style=\"font-size: 16.0pt;font-family: simsun;\"><br class=\"img-brk\"><br class=\"img-brk\"><br></span></strong></span></p>"
}
```
