## Document Structure for switch Button
In this dedicated section, you will gain familiarity with a dynamic element that empowers you with the versatile flexibility to rearrange the structure of your dashboard pages according to your preferences and needs.

## Basic usage
- Required string param **kind** always should be **Switch**.
- Required string param **version** is **v1**.
- Required list param **type**, always should be **Switch**
- Required string param **name**, data key for this field's payloads.
- Optional string param **label** is name of your Switch.


Incorporate these details into the provided template to create a well-structured switch Button.

```json
{
  "kind": "Switch",
  "version": "v1",
  "type": "Switch",
  "name": "Switch",
  "label": "switch mode"
}
```

