## Document Structure for area trend chart

In this section, you can specify the value of the element's data.
## Basic usage

- Required string param **version** is **v1**.
- Required string param **kind** always should be **sticky-stat**.
- Required integer param **value**, your data value for example _200_.
- Required string param **title**, your title data for example _New Issues_.

```json

{
  "version": "v1",
  "kind": "sticky-stat",
  "value": 200,
  "title": "New Issues"
}
```

## Set color
You can set color for element.

```json
{
  "version": "v1",
  "kind": "sticky-stat",
  "value": 214,
  "title": "New Issues",
  "color": "#000000"
}
```


## Set element size
You can choose between two sizes, small and large, for defining the size of your element.
```json
{
  "version": "v1",
  "kind": "sticky-stat",
  "value": 214,
  "color": "#000000",
  "title": "New Issues",
  "size": "large"
}
```
