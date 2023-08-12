## Document Structure for Creating page

In this dedicated section, you will gain familiarity with a dynamic element that empowers you with the versatile
flexibility to rearrange the structure of your dashboard pages according to your preferences and needs.

The page is an inheritance of flex. And this section is exactly similar to the flex section. You can refer
to [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.

## Basic usage

- Required string param **kind** always should be **page**.
- Required string param **version** is **v1**.
- Required list param **children**, You can refer to
  the [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.
- Required string param **uri** is the address of page for example `/customers`.

Incorporate these details into the provided template to create a well-structured flex element.

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/"
}
```

### Create Responsive Page

For make responsive and flexible `Page` you can add **className** param, You can refer to
the [flex document](https://github.com/airdashio/documentation/blob/main/docs/_posts/flex.md) for more information.

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "classname": "flex"
}
```

### Set Title for Page

For setting a title for the `Page` you can add **title** param.

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "title": "SaleForce"
}
```

### Create Specific Variables

**variables** is a dictionary param that allow customer to create and use specific variables in `page`.

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "title": "SaleForce"
}
```

#### Usage

```json
{
  "kind": "page",
  "version": "v1",
  "variables": {
    "platform": "AIRDASH",
    "licensed": "https://www.monirs.com"
  },
  "children": [
    {
      "kind": "heading",
      "version": "v1",
      "title": "Analytics dashboard",
      "subtitle": "I love using {{variables.platform}}} for create wonderful dashboards; their site is {{variables.licensed}}}."
    }
  ],
  "uri": "/"
}
```

### Create Specific Templates

**templates** is a dictionary param that allow customer to create and use specific templates in `page`.

```json
{
  "kind": "page",
  "version": "v1",
  "templates": {
    "heading": {
      "kind": "heading",
      "version": "v1",
      "title": "Analytics dashboard",
      "subtitle": "I love using {{variables.platform}}} for create wonderful dashboards; their site is {{variables.licensed}}}."
    }
  },
  "children": [
  ],
  "uri": "/"
}
```

#### Usage

```json
{
  "kind": "page",
  "version": "v1",
  "templates": {
    "heading": {
      "kind": "heading",
      "version": "v1",
      "title": "Analytics dashboard",
      "subtitle": "I love using {{variables.platform}}} for create wonderful dashboards; their site is {{variables.licensed}}}."
    }
  },
  "children": [
    {
      "template": "heading"
    },
    {
      "template": "heading"
    },
    {
      "template": "heading"
    }
  ],
  "uri": "/"
}
```

### Navigation Options

**navigation** is a string and dictionary param, which has various options such as `null` for remove
current `navigation` and `inherit` for use previous `navigation` and new navigation configuration for overwrite
previous `navigation`, you can see more information
here [navigation](https://github.com/airdashio/documentation/blob/main/docs/_posts/navigation.md) for make
new `navigation`.

#### Use `inherit`

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "navigation": "inherit"
}
```

#### Use `null`

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "navigation": null
}
```

#### Overwrite Previous Navigation

```json
{
  "kind": "page",
  "version": "v1",
  "children": [],
  "uri": "/",
  "navigation": {
    "kind": "navigation",
    "version": "v1",
    "default": {
      "url": "https://example.com/first_page",
      "headers": {},
      "payload": {}
    }
  }
}
```
