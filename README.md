# Best Buy Scraper

### How it works

You can get Best Buy results by providing your own URLs to our service. We can return the HTML of any Best Buy page you like.

#### Python code example

The example below illustrates how you can get an eBay product page result in HTML format.

```python
import requests
from pprint import pprint

# Structure payload.
payload = {
    'source': 'universal_ecommerce',
    'url': 'https://www.bestbuy.com/site/samsung-galaxy-z-flip4-128gb-unlocked-graphite/6512618.p?skuId=6512618',
    'geo_location': 'United States',
    'parse': True,
}

# Get response.
response = requests.request(
    'POST',
    'https://realtime.oxylabs.io/v1/queries',
    auth=('user', 'pass1'),
    json=payload,
)

# Instead of response with job status and results url, this will return the
# JSON response with the result.
pprint(response.json())
```

Find code examples for other programming languages [**here**](https://github.com/oxylabs/best-buy-scraper/tree/main/code%20examples)

#### Output Example

```json
{
    "results": [
        {
            "content": {
                "url": "https://www.bestbuy.com/site/samsung-galaxy-z-flip4-128gb-unlocked-graphite/6512618.p?skuId=6512618&intl=nosplash",
                "price": {
                    "price": 999.99,
                    "currency": "USD"
                },
                "title": "Samsung - Galaxy Z Flip4 128GB (Unlocked) - Graphite",
                "rating": {
                    "count": 0,
                    "score": 0
                },
                "product_id": "6512618",
                "is_sold_out": null,
                "parse_status_code": 12000,
                "additional_information": [
                    {
                        "name": "Model",
                        "value": "SM-F721UZAAXAA"
                    },
                    {
                        "name": "SKU",
                        "value": "6512618"
                    },
                    {
                        "name": "Release Date",
                        "value": "08/26/2022"
                    }
                ]
            },
            "created_at": "2022-08-18 14:00:57",
            "updated_at": "2022-08-18 14:01:01",
            "page": 1,
            "url": "https://www.bestbuy.com/site/samsung-galaxy-z-flip4-128gb-unlocked-graphite/6512618.p?skuId=6512618&intl=nosplash",
            "job_id": "6966031187999462401",
            "status_code": 200,
            "parser_type": "bestbuy_product"
        }
    ]
}
```
