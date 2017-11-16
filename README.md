# jQuery Bootstrap Form Validation

Author: <i>Timo Fischer</i>

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
            type: 'validation_type', // default: none
            prompt: 'enter error prompt message', // default: none
            showSuccess: false // default: true; show success status for form-group
        }
    }, // add more fields here 
    ],
    submitOnValid: false, // default: true
    showErrorMessage: true, // default: true
    errorMessageText: "Custom Error Message", // default: "Please check the fields below."
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

### Tested Systems
- [X] Chrome v62 on Windows
- [X] Firefox v56 on Windows
- [X] Internet Explorer v11 on Windows
- [X] Microsoft Edge v25 on Windows
- [X] Chrome v62 on Mac
- [X] Firefox v56 on Mac
- [X] Safari v11 on Mac
