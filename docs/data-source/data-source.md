# Using Data Sources

`AIRDASH` allows users to connect to APIs that provide data in JSON format, enabling them to fetch information in
real-time or batch mode. This feature empowers users to seamlessly integrate data into their visualizations and reports,
whether it's for live updates or batch analysis, thereby gaining deeper insights and uncovering new perspectives.

In `AIRDASH`, users have the flexibility to utilize `Data Sources` as inputs for different elements, even within
specific sections or pages. This adaptability greatly enhances the user experience, making it easier to integrate
datasets into various parts of the platform and improving overall usability.

## Data Source

`AIRDASH` offers users various capabilities for defining data sources, among which is the ability to configure data
sources statically.

### Make Static Data Source

**The `data` should be defined in a `page` template, but usable across all other elements.**

- Required string param **id** and must be unique.
- Required string param **source-type** that should be static for a `static-data-source`.

```json
{
  "kind": "page",
  "version": "v1",
  "uri": "/",
  "data": [
    {
      "id": "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb",
      "source-type": "static",
      "data": [
        22,
        65,
        43
      ]
    }
  ],
  "elements": []
}
```

## Multi Data Sources

`AIRDASH` offers users the capability to define data sources based on APIs, both individually and in a composite manner.
This empowers users to utilize multiple data sources for input information for each element, page, or segment of a page.

**The `data` should be defined in a `page` template, but usable across all other elements.**

- The `default` value serves as a strategic measure to prevent users from encountering
  loading delays and a suboptimal user experience when dealing with substantial data retrieval. This predefined dataset
  offers users an initial engagement point, effectively mitigating potential loading bottlenecks and optimizing their
  experience until the remaining data is seamlessly fetched.
- 
- To populate the required data in the payload of your desired request, you should utilize the `payload` parameter.
- To populate the required data in the headers of your desired request, you should utilize the `headers` parameter.
- To set endpoint for your desired request, you need to populate the `url` parameter.
- Required string param **source-type** that should be static for a `api`.

```json
{
  "kind": "page",
  "version": "v1",
  "uri": "/",
  "data": [
    {
      "id": "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb",
      "source-type": "api",
      "url": "https://example.com/api/customer_profile",
      "headers": {},
      "payload": {
        "name": "john"
      }
    }
  ],
  "elements": []
}
```

## Lazy Data Loading

`AIRDASH` provides users with a valuable feature to tackle heavy datasets: the "Lazy Loading" capability. This
functionality starts by showcasing default data and gradually fetches and presents the main dataset, ensuring a seamless
and efficient user experience.

**The `data` should be defined in a `page` template, but usable across all other elements.**

- Step-by-Step Data Loading : AIRDASH has implemented a gradual data fetching approach for handling heavy datasets,
  enhancing the data retrieval process. Instead of fetching all data within a single data source, AIRDASH allows data to
  be defined in multiple data. This step-by-step approach enables AIRDASH to fetch and display data progressively for
  users.

```json
{
  "kind": "page",
  "version": "v1",
  "uri": "/",
  "data": [
    {
      "id": "7193df95-9049-4ab5-b18c-0abcc8edd9c3",
      "url": "https://example.com/api/weekly_sells_count",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 0,
        "limit": 200
      }
    },
    {
      "id": "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb",
      "payload": {
        "start": 201,
        "limit": 400
      },
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "url": "https://example.com/api/weekly_sells_count"
    }
  ],
  "elements": []
}
```


## Examples

### several Api and Static `data-source` and `default` Value and `lazy-data-loading` operation:

```json
{
  "kind": "page",
  "version": "v1",
  "data": [
    {
      "id": "7193df95-9049-4ab5-b18c-0abcc8edd9c3",
      "source-type": "api",
      "url": "https://example.com/api/weekly_sells_count",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 0,
        "limit": 200
      }
    },
    {
      "id": "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb",
      "source-type": "api",
      "url": "https://example.com/api/weekly_sells_count",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 201,
        "limit": 400
      }
    },
    {
      "id": "7a9b3a14-40f7-46c1-a4da-87742f53bd7e",
      "source-type": "api",
      "url": "https://example.com/api/daily_sells",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 0,
        "limit": 90
      }
    },
    {
      "id": "ca4e91a2-81f0-482e-8100-2f52e3531a84",
      "source-type": "api",
      "url": "https://example.com/api/daily_sells",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 91,
        "limit": 180
      }
    },
    {
      "id": "9854bc65-a1fe-4182-9a6d-f0046f4add33",
      "source-type": "static",
      "data": [
        22,
        65,
        43
      ]
    }
  ],
  "elements": [
    {
      "version": "v1",
      "kind": "circular-distribution",
      "series": {
        "data-source": [
          "7193df95-9049-4ab5-b18c-0abcc8edd9c3",
          "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb"
        ],
        "default": [
          15,
          20,
          38,
          27
        ]
      }
    },
    {
      "version": "v1",
      "kind": "circular-distribution",
      "series": {
        "data-source": [
          "7a9b3a14-40f7-46c1-a4da-87742f53bd7e"
        ],
        "default": [
          22,
          64,
          27,
          96
        ]
      }
    },
    {
      "version": "v1",
      "kind": "circular-distribution",
      "series": {
        "data-source": [
          "9854bc65-a1fe-4182-9a6d-f0046f4add33",
          "ca4e91a2-81f0-482e-8100-2f52e3531a84"
        ],
        "default": [
          22,
          64,
          27,
          96
        ]
      }
    }
  ],
  "uri": "/"
}
```


### several Api and Static `data-source` and `default` Value:


```json
{
  "kind": "page",
  "version": "v1",
  "data": [
    {
      "id": "7193df95-9049-4ab5-b18c-0abcc8edd9c3",
      "source-type": "api",
      "url": "https://example.com/api/weekly_sells_count",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 0,
        "limit": 200
      }
    },
    {
      "id": "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb",
      "source-type": "api",
      "url": "https://example.com/api/weekly_sells_count",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "start": 201,
        "limit": 400
      }
    },
    {
      "id": "7a9b3a14-40f7-46c1-a4da-87742f53bd7e",
      "source-type": "api",
      "url": "https://example.com/api/daily_sells",
      "headers": {
        "Authorization": "Bearer <your-access-token>"
      },
      "payload": {
        "product_key": "Pr21"
      }
    }
  ],
  "elements": [
    {
      "kind": "flex",
      "version": "v1",
      "elements": {
        "data-source": [
          "7193df95-9049-4ab5-b18c-0abcc8edd9c3",
          "01ff61ca-2e47-4ebe-b076-7aa9491fcbcb"
        ],
        "default": []
      },
      "className": "flex"
    },
    {
      "kind": "flex",
      "version": "v1",
      "elements": {
        "data-source": [
          "7a9b3a14-40f7-46c1-a4da-87742f53bd7e"
        ],
        "default": []
      },
      "className": "flex"
    }
  ],
  "uri": "/"
}
```

