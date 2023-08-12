## Document Structure for Creating Navigation

In AIRDASH we provide users with the capability to customize the arrangement of dashboard pages and the navigation menu
for each individual user.

### Basic usage
- Required string param **kind** always should be **navigation**.
- Required string param **version** is **v1**.
- Required dictionary param **default** is the first page that is seen by the user. 

```json
{
  "kind": "navigation",
  "version": "v1",
  "default": {
    "url": "https://example.com/first_page",
    "headers": {},
    "payload": {}
  }
}
```

### Make a Simple Navigation Menu
  - **items** is a list of dictionaries param that allow customer to create navigate menu.
  - **title** is a string param which represents the displayed name of your menu icon.
  - **type** is a string param that determines the subtype of your menu item, which has various options such as `group` and `collapse`.
  - **icon** is a string param that you can choose your preferred icon following the structure of [material-icons](https://mui.com/material-ui/material-icons/).
  - **data** is a dictionary param, check [data-source](https://github.com/airdashio/documentation/blob/main/docs/_posts/data-source.md) for more information
  - **path** is a string param that rewrites and specifies the page's position relative to a previous endpoint.

```json
{
  "kind": "navigation",
  "version": "v1",
  "default": {
    "url": "https://example.com/first_page",
    "headers": {},
    "payload": {}
  },
  "items": [
    {
      "id": "3012d074-ed53-492e-8b6e-1730c89b647b",
      "title": "Businesses Management",
      "type": "item",
      "icon": "apps",
      "data": {
        "url": "https://fca75e4ec56fcca.monirs.ir/pwa/business/dashboard_businesses",
        "payload": {},
        "headers": {},
        "path": "/businesses"
      }
    }
  ]
}

```

### Make a Group Type Navigation Menu

```json
{
  "kind": "navigation",
  "version": "v1",
  "default": {
    "url": "https://example.com/first_page",
    "headers": {},
    "payload": {}
  },
  "items": [
    {
      "id": "3012d074-ed53-492e-8b6e-1730c89b647b",
      "title": "Businesses Management",
      "type": "group",
      "icon": "apps",
      "children": [
        {
          "id": "37f9bb50-7b3c-4c17-b952-965d45b97de2",
          "title": "Your Businesses",
          "type": "item",
          "data": {
            "url": "https://example.com/businesses",
            "headers": {},
            "payload": {},
            "path": "/businesses"
          }
        },
        {
          "id": "8898fc9e-b29d-477c-9620-2ee0f1e0a97f",
          "title": "Your Customers",
          "type": "item",
          "data": {
            "url": "https://example.com/customers",
            "headers": {},
            "payload": {},
            "path": "/customers"
          }
        }
      ]
    }
  ]
}
```

### Make a Collapse Type Navigation Menu

```json
{
  "kind": "navigation",
  "version": "v1",
  "default": {
    "url": "https://example.com/first_page",
    "headers": {},
    "payload": {}
  },
  "items": [
    {
      "id": "3012d074-ed53-492e-8b6e-1730c89b647b",
      "title": "Businesses Management",
      "type": "collapse",
      "icon": "apps",
      "children": [
        {
          "id": "3012d074-ed53-492e-8b6e-1730c89b647b",
          "title": "Businesses Management",
          "type": "group",
          "icon": "apps",
          "children": [
            {
              "id": "37f9bb50-7b3c-4c17-b952-965d45b97de2",
              "title": "Your Businesses",
              "type": "item",
              "data": {
                "url": "https://example.com/businesses",
                "headers": {},
                "payload": {},
                "path": "/businesses"
              }
            },
            {
              "id": "8898fc9e-b29d-477c-9620-2ee0f1e0a97f",
              "title": "Your Customers",
              "type": "item",
              "data": {
                "url": "https://example.com/customers",
                "headers": {},
                "payload": {},
                "path": "/customers"
              }
            }
          ]
        },
        {
          "id": "8898fc9e-b29d-477c-9620-2ee0f1e0a97f",
          "title": "Your Products",
          "type": "item",
          "data": {
            "url": "https://example.com/products",
            "headers": {},
            "payload": {},
            "path": "/products"
          }
        }
      ]
    }
  ]
}
```

