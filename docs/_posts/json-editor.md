---
title: JSON Editor
author: cotes
date: 2023-03-08 14:10:00 +0800
categories: [ Blogging, Tutorial ]
tags: [ writing ]
render_with_liquid: false
---

## Document Structure for Creating JSON Editor

In this section, you will become familiar with a tool that provides you with the capability to edit code using the JSON
format through a form.

## Basic usage

- Required string param **kind** always should be **code-editor-json**.
- Required string param **version** always should be **v1**.
- Required string param **name** is name of your form editor.
- Required dictionary param **placeholder** display everything you need in the placeholder.
- Required integer param **height** a numerical value used to set the height of your form's display.

Incorporate this information into the provided template to create a well-structured element relevant to editing
JSON-formatted forms.

```json
{
  "kind": "code-editor-json",
  "version": "v1",
  "name": "JsonEditor",
  "placeholder": {
    "example": {
      "my customer name": "Tom"
    }
  },
  "height": 288
}
```




