## Document Structure for Creating Text Field

In this section, you will become familiar with a tool that provides you with the capability to edit text-field.

## Basic usage

- Required string param **kind** always should be **code-editor-json**.
- Required string param **version** always should be **v1**.
- Required string param **name** data key for this field's payloads.

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


## Set initial content 
- The **default** is an optional string parameter used in a text field to pre-fill initial content, assisting user input. It's often employed for placeholders or suggestions.

```json
{
  "kind": "text-field",
  "version": "v1",
  "name": "text-field",
  "default": ""
}

```


## Set label
- The **label** is an optional string parameter that serves as the name of your `text-field`.

```json
{
  "kind": "text-field",
  "version": "v1",
  "name": "text-field",
  "default": "",
  "label": "Text Field Title"
}
```
