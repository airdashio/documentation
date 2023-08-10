---
title: Text Field
author: cotes
date: 2023-03-08 14:10:00 +0800
categories: [ Blogging, Tutorial ]
tags: [ writing ]
render_with_liquid: false
---

## Document Structure for Creating Text Field

In this section, you will become familiar with a tool that provides you with the capability to edit text-field.

## Basic usage

- Required string param **kind** always should be **code-editor-json**.
- Required string param **version** always should be **v1**.
- Required string param **name** data key for this field's payloads.
- Optional string param **default** in a text field pre-fills initial content, aiding user input, often used for placeholders or suggestions..
- Optional integer param **label** is name of your `text-field`.

Incorporate this information into the provided template to create a well-structured element relevant to editing
text forms.

```json
{
  "kind": "text-field",
  "version": "v1",
  "name": "text-field",
  "default": "",
  "label": "Text Field Title"
}

```




