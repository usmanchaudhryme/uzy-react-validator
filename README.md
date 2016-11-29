# uzy-react-validator

Best way to introduce validations into components.


Example:
Given example is in coffeescript, but of course you may use the example from examples directory. 

```
Validtor = require 'uzy-react-validator'

onSubmit: (e) =>
  e.preventDefault()
  if Validator.formIsValid(@refs)
    # Do your thing
render: 
form className: 'form', onSubmit: @onSubmit,
  React.createElement InputFieldExtended,
    name          : 'profile[firstname]'
    label         : 'First name'
    placeholder   : 'e.g. Johnny'
    ref           : 'first_name'
    validators    : ['required']
    errorTitle    : 'First name'
  React.createElement DatePickerCalendar,
    name          : 'profile[date_of_birth]'
    label         : 'Your Birthdate'
    validators    : ['dateNotGreaterThanToday', {method: 'dateOlderThan', params: [10]}]
    errorTitle    : 'Your birthdate'
    ref           : 'dateOfBirth'
      
```
