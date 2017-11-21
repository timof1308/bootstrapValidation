# jQuery Bootstrap Form Validation

![Version](https://img.shields.io/badge/Author-Timo_Fischer-red.svg)
![MIT License](https://img.shields.io/github/license/mashape/apistatus.svg)
![Version](https://img.shields.io/badge/Version-1.1.0-green.svg)


## Getting started
1. download `validator.js` from repository
2. include this file to your project
3. make sure your HTML-syntax looks like this:
```html
<div class="form-group">
    <label class="control-label" for="input_id">Required</label>
    <input type="text" id="input_id" class="form-control" name="input_name">
</div>
```
4. initialize form validation with
```javascript
var form = new Validation('#form_id', {
    fields: [{
        name: 'input_name',
        rule: {
            type: 'validation_type', // check out validation rules; default: none
            prompt: 'enter error prompt message', // default: none
            showSuccess: false // default: true; show success status for form-group
        }
    }, // add more fields 
    ],
    submitOnValid: false, // default: true
    errorMessageText: "Custom Error Message", // default: "Please check the fields below."
    errorGroupClass: "has-error has-feedback", // set error class for form-group
    successGroupClass: "has-success has-feedback" // set success class for form group
});
```
5. validation gets triggered when user submits the form

reset your form with:
```javascript
form.reset();
```

open `index.html` with your browser for live demo

### Validation Rules

| Pattern | Explanation |
|---|---|
| required | any word characters | 
| e-mail | any valid e-mail address | 
| minLength:X | value must be at least X characters long | 
| maxLength:X | value cannot be longer than X characters | 
| regex:X | regex check for value | 
| checked | check if checkbox / radio is checked |

### Parameter Options
| Option | Explanation | default |
|---|---|---|
|`fields.name`| HTML input name to identify input element | none |
|`fields.rule.type`| Specify validation pattern for this input name. See [Validation Rules](#validation-rules) for more information | none |
|`fields.rule.prompt`| Create `.help-block` with prompt text to display error message on invalid input | none |
|`fields.rule.showSuccess`| Show success status for `.form-group` on valid input | true |
| submitOnValid | Action after form validation <br> - `true`: submit form and navigate to form action route <br> - `false`: triggered callback <br> See [Form Callbacks](#form-callbacks) for more information | true |
| showErrorMessage | Show alert-danger on invalid form | true |
| errorMessageText | Customize alert-danger message | "Please check the fields below." |
| errorGroupClass | Set your own error-class for `.form-group` on error | "has-error" |
| successGroupClass | Set your own success-class for `.form-group` on success | "has-success" |

#### Form Callbacks
- `is-valid` callback for valid form fields on subimt submit
- `is-invalid` callback for invalid form fields on form submit

### Tested Systems
- [X] Chrome v62 on Windows
- [X] Firefox v56 on Windows
- [X] Internet Explorer v11 on Windows
- [X] Microsoft Edge v25 on Windows
- [X] Chrome v62 on Mac
- [X] Firefox v56 on Mac
- [X] Safari v11 on Mac

#### Changelog
- 1.1.0: Added custom error and success class options for `form-group`