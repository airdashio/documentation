---
title: page
author: amir pahlevani
date: 2023-03-08 14:10:00 +0800
categories: [Blogging, Tutorial]
tags: [writing]
render_with_liquid: false
---

## Document Structure for Creating page
In this dedicated section, you will gain familiarity with a dynamic element that empowers you with the versatile flexibility to rearrange the structure of your dashboard pages according to your preferences and needs.

The page is an inheritance of flex. And this section is exactly similar to the flex section. You can refer to [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.
## Basic usage
- Required string param **kind** always should be **page**.
- Required string param **version** is **v1**.
- Required list param **children**, You can refer to the [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.
- Required string param **className**, You can refer to the [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.
- Required string param **uri** is the address of page for example `/customers`.
- Optional string param **title** is the title of page for example _AIRDASH_.
- Optional string param **navigation_id** your navigation_id, for more information you refer []().

Incorporate these details into the provided template to create a well-structured flex element.

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "className": "flex",
  "uri": "/",
  "title": "AIRDASH",
  "navigation_id": "cbf6601a-06c1-4ec8-8103-1b4816aea48e",
  "data": [
    {
      "id": "fb1471e0-4187-4760-ac7a-77564f5975bc",
      "payload": {},
      "headers": {},
      "url": ""
    }
  ],
  "variables": {
    "platform": "AIRDASH",
    "licensed": "https://www.monirs.com"
  },
  "templates": {
    "book": {
      "bookName": "The Hard Things about Hard Things",
      "categoryId": 87564521
    }
  }
}

```

