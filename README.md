## Validate Form
A tiny vanilla JS library for validating form elements.

## What's the syntax?
The syntax is straight forward. Every element that needs to be validated 
should have the same `class` name, a `data-regex` value and a 
`data-alert` value.

## What's `data-regex`?
`data-regex` accepts any valid JS regular expression as a string. So if 
you'd need to validate a form input that accepts 0 or more characters, 
set `data-regex` to `.*`, and for 1 or more characters, set it to `.+`.

## What's `data-alert`?
`data-alert` is the statement that will be set as the placeholder value 
of the validating form element, after clearing out the entered value, in 
case validation fails.

## What about passwords?
The library also has the functionality to validate passwords. Just use 
the same class name across all the elements that need validation, and in 
case `Validate-Form` comes across `<input type="password">`, it 
automatically ensures that the password entered matches any other 
`<input type="password">` that it might come across in the page.

## How do I validate my form?
`var validated = validate_form(form_id, form_elements_class);`
`validate_form` accepts 2 parameters --> 
1. `form_id`, which is the `id` of the elements' enclosing `div`, or `form`. It doesn't matter if the enclosing section is a `p`, `span`, a `div` or a `form`, since the library only queries for all elements under the same `id`.
2. `form_elements_class`, which is the class assigned to all the 
elements that need to be validated. Under the hood, `validate_form` uses 
`getElementsByClassName`, so all the elements in a form need to have the 
same class name.