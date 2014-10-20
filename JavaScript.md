
## Variable declaration.

Use `camelCase` convention over `snake_case`.

```js
// Bad example.
var stars_counter = 10;

// Good example.
var starsCounter = 10;
```

## Reserved words.

Avoid using these words in variables and functions:

`event`, `native`, `class` and other JavaScript [reserved words](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Reserved_keywords_as_of_ECMAScript_6).

## Function declaration.

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
$('a').click(function(e) {
    $(this).hide();
});

```
