# Ajax Application

## Intro
[Mezon Framework](https://github.com/alexdodonov/mezon) provides simple class for creating ajax applications. This class uses all functionality of the [Mezon Application Class](https://github.com/alexdodonov/mezon-application) also provides usefull functionality:

- automatic creation of the routes '{RouteName}' from methods like 'action{RouteName}';
- [routes setup from config](https://github.com/alexdodonov/mezon-application#loading-routes-from-config-file).
- [action messaging](https://github.com/alexdodonov/mezon-application#action-messages).

## Installation

Just print in console

```
composer require mezon/ajax-application
```

And that's all )

# Learn more

More information can be found here:

- [Mezon Framework](https://github.com/alexdodonov/mezon)
- [Twitter](https://twitter.com/mezonphp)
- [Dev.to](https://dev.to/alexdodonov)
- [Medium](https://gdvever.medium.com/)

# I'll be very glad if you'll press "STAR" button )

# Exception handling

For better debugging exception handling is performed in a special way. If the ajax request will be failed to process, then on the front end you will get JSON object with fields:

- *code* - code of the occured error;
- *message* - textual description of the occured error;
- *call_stack* - call stack for the call wich lead to the error.

# Finishing request processing

After finishing request processing you can mark it as successfull:

```php
function ajaxRequestSuccess(): void
```

Wich will return `{"code": 0}`

Or return any other result:

```php
function ajaxRequestResult($result): void
```

In this case $result will be encoded in JSON and outputted.

Or in case of the error you can call

```php
function ajaxRequestError(string $message, int $code = - 1): void
```

Wich will return object `{"code": $code, "message": "message"}`