## Document Structure for Creating Flexs
In this dedicated section, you will gain familiarity with a dynamic element that empowers you with the versatile flexibility to rearrange the structure of your dashboard pages according to your preferences and needs.
## Basic usage
By following this structure, create the heading section effectively in your dashboards.
- Required string param **kind** always should be **flex**.
- Required string param **version** is **v1**.
- Required list param **elements** your elements.
- Required string param **className** your required layout type for the elements and support [tailwind's flex items](https://www.tailwindcss.com/docs/flex).


Incorporate these details into the provided template to create a well-structured flex element.

```json
{
  "kind": "flex",
  "version": "v1",
  "elements": [],
  "className": "flex"
}
```

## Tables

| flex           | classes           |                      Properties |
|:---------------|:------------------|--------------------------------:|
| Flex Basis     | basis-0           |                flex-basis: 0px; |
| Flex Basis     | basis-3           |  lex-basis: 0.75rem; /* 12px */ |
| Flex Basis     | basis-6/12        |                flex-basis: 50%; |
| Flex Direction | flex-row          |            flex-direction: row; |
| Flex Direction | flex-row-reverse  |                  Flex Direction |
| Flex Direction | flex-col          |         flex-direction: column; |
| Flex Direction | flex-col-reverse  | flex-direction: column-reverse; |
| Flex Wrap      | flex-wrap         |                flex-wrap: wrap; |
| Flex Wrap      | flex-wrap-reverse |        flex-wrap: wrap-reverse; |
| Flex Wrap      | flex-nowrap       |              flex-wrap: nowrap; |
| Flex           | flex-1            |                   flex: 1 1 0%; |
| Flex           | flex-auto         |                 flex: 1 1 auto; |
| Flex           | flex-initial      |                 flex: 0 1 auto; |
| Flex           | flex-none         |                     flex: none; |
| Flex Grow      | grow              |                  flex-grow: 1;  |
| Flex Grow      | grow-0            |                  flex-grow: 0;  |
| Flex Shrink    | shrink            |                 flex-shrink: 1; |
| Flex Shrink    | shrink-0          |                 flex-shrink: 0; |





