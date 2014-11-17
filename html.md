
## HTML style guide

Standards for writing clean and readable HTML.

### Generalities

    * Use 4 spaces tab
    * Leave line breaks between blocks

### Template statements

In order for statements to be readable in templates, we've decided to unindent them one tab so 
that they're hightlighted, easy to spot and don't get misread as bare HTML.

> Bad example


```html
<div class="header">
    <div class="container">
      {% if a == b %}
        <h1>Equal</h1>
      {% endif %}
    </div>
</div>
```

> Good example 

```html
<div class="header">
    <div class="container">
  {% if a == b %}
      <h1>Equal</h1>
  {% endif %}
    </div>
</div>
```


### Indentation

Make sure that child elements are indented one tab. 

> Bad example

```html
<div class="header">
    <div class="container">
        <div class="row">
      <h1>Equal</h1>
    </div>
</div>
```

> Good example

```html
<div class="header">
    <div class="container">
      <h1>Equal</h1>
    </div>
</div>
```

