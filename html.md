
## HTML style guide

Standards for writing clean and readable HTML.

### Template statements

In order for statements to be readable in templates, we've decided to unindent them one tab so 
that they're hightlighted, easy to spot and don't get misread as bare HTML.

**Bad example**

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
