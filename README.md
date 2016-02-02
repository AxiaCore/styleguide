# AxiaCore Coding Styleguide

This is how we should write code.

## Commit messages

* If it's necessary, you can add the Jira ticket id to the commit E.G:
`MA-1 Added something...` or the Sentry issue number `#123 Fixes bug...`
* Commit messages can also start with an emoji.
    * :lollipop: `:lollipop:` when improving code format and structure
    * :art: `:art:` when making visual changes
    * :bug: `:bug:` when fixing bugs
    * :memo: `:memo:` when writing documentation
    * :fire: `:fire:` when removing unused code
    * :sunny: `:sunny:` alternative emoji for a general improvement
    * :white_check_mark: `:white_check_mark:` when fixing tests

## CSS

Standars for writing styles mainly using SASS.

### Variables

Embrace the use of sass variables, and when possible avoid using direct color
codes to elements, instead create a variable for such code.

### Frameworks

- Bourbon


## Python

Things should be short and easy to understand.

### Generalities
* Use single quotes `''` for strings.
* Use underscore in templates names.

### URLS

Use `/` slash at the end of all URLs

> Incorrect example

```python
r'^(?P<slug>[-\w]+)/settings$'
```

> Correct example

```python
r'^(?P<slug>[-\w]+)/settings/$'
```

### Includes

Use an include for every dependency, even if they're under the same package.

> Bad example

```python
from app.views import HomeView, NewsletterView, WidgetView
```

> Good example

```python
from app.views import HomeView
from app.views import NewsletterView
from app.views import WidgetView
```

### Comments

Preferably, use docstrigns when describing classes and methods behaviour.

> Bad example

```python
class UserForm(UpdateView):
    # Form for updating user info.

  ...
```

> Good example

```python
class UserForm(UpdateView):
    """ Form for updating user info.
    """

    ...
```

### Get context

Use direct assignment when passing a single variable to contex

> Bad example

```python
def get_context_data(self, **kwargs):
    ...

    context.update({
        'comment_form': CommentForm,
    })

    ...
```

> Good example

```python

def get_context_data(self, **kwargs):
    ...

    context['comment_form'] = CommentForm

    ...
```


## HTML

* Use 4 spaces tab
* Leave line breaks between blocks

### Template statements

In order for statements to be readable in templates, we've decided to unindent
them one tab so that they're hightlighted, easy to spot and don't get misread
as bare HTML.

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
</div>
```

> Good example

```html
<div class="header">
   <div class="container">
        <div class="row">
            <h1>Equal</h1>
        </div>
    </div>
</div>
```

### Attributes
Don't use spaces before and after equals '='.

> Bad example

```html
<div class = "header"></div>
```

> Good example

```html
<div class="header"></div>
```

### Comparisons

Using `is`, `is not` vs  `==` and `!=`

`==` is an equality test. It checks whether the right hand side and the left hand side are equal objects (according to their __eq__ or __cmp__ methods.)

`is` is an identity test. It checks whether the right hand side and the left hand side are the very same object. No methodcalls are done, objects can't influence the is operation.

You use is (and is not) for singletons, like `None`, where you don't care about objects that might want to pretend to be None or where you want to protect against objects breaking when being compared against None.

From: http://stackoverflow.com/questions/2209755/python-operation-vs-is-not

## JavaScript

### Variable declaration.

Use `camelCase` convention over `snake_case`.

```js
// Bad example.
var stars_counter = 10;

// Good example.
var starsCounter = 10;
```

### Assigning `this`.

When assigning `this` to a variable name the variable `that`.
```js
var that = this;

....
$('..').on('click', function() {
   $(that)...
});
```

### Reserved words.

Avoid using these words in variables and functions:

`event`, `native`, `class` and other JavaScript [reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Reserved_keywords_as_of_ECMAScript_6).

### Function declaration.

Add a space after function closing parenthesis.


```js
// Bad example.
function baz(fum, bar){
    // Do stuff...
}

// Good example.
function baz(fum, bar) {
    // Do stuff...
}
```

Use `this` within jQuery callbacks to refer to current element.

```js
// Bad example.
$('a').click(function(e) {
    $(e.target).hide();
});

// Good example.
$('a').on('click', function() {
    $(this).hide();
});

```
