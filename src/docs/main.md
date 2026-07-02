## `error`

```ab
pub fun error(message: Text, with_timestamp: Bool = false): Null 
```

Prints an error message with predefined format

## `error_exit`

```ab
pub fun error_exit(message: Text, code: Int = 1, with_timestamp: Bool = false, monotone: Bool = false): Null 
```

Prints an error message with predefined format and exits with specified exit code

## `error_fail`

```ab
pub fun error_fail(message: Text, code: Int = 1, with_timestamp: Bool = false, monotone: Bool = false): Null? 
```

Prints an error message with predefined format and fails with specified code

## `lib_error`

```ab
fun lib_error(message: Text): Null? 
```

## `log`

```ab
pub fun log(message: Text, with_timestamp: Bool = false): Null 
```

Prints a log message with predefined format

## `success`

```ab
pub fun success(message: Text, with_timestamp: Bool = false): Null 
```

Prints a success message with predefined format

## `throw`

```ab
pub fun throw(type: Text, arguments: [Text], position: Int, correct: Text = ""): Null? 
```

Throw a predefined error template

Default types:
- "invalid-arg": "Invalid argument" error
- `position` represents the array index of the invalid argument
- If `correct` is supplied, an extra "Did you mean <correct>?" is printed
- "too-few-args": "Too few arguments" error
- `position` represents the minimum amount of arguments
- If `correct` is supplied, it shows as a placeholder to one of the missing arguments
- "missing-value": "Option requires a value" error
- `position` represents the array index of the argument
- If `correct` is supplied, it shows as a value placeholder for the option
- "invalid-value": "Option expects type" error
- `position` represents the array index of the argument
- `correct` is mandatory in `<ValueType> <RequiredType>` format, separated by a comma. Arrays are not supported

Note: `arguments[0]` is consumed as the script name, use custom name if you're using custom arguments array

## `update_error_format`

```ab
pub fun update_error_format(prefix_style: Text, monotone: Bool = false): Null 
```

Supported prefix styles: `default`, `classic`, `minimal`, `inverted` or custom

## `update_format`

```ab
pub fun update_format(prefix: Text = PREFIX_FORMAT, monotone: Bool = false) 
```

Reloads all formats

## `update_log_format`

```ab
pub fun update_log_format(prefix_style: Text, monotone: Bool = false): Null 
```

Supported prefix styles: `default`, `classic`, `minimal`, `inverted` or custom

## `update_success_format`

```ab
pub fun update_success_format(prefix_style: Text, monotone: Bool = false): Null 
```

Supported prefix styles: `default`, `classic`, `minimal`, `inverted` or custom

## `update_warn_format`

```ab
pub fun update_warn_format(prefix_style: Text, monotone: Bool = false): Null 
```

Supported prefix styles: `default`, `classic`, `minimal`, `inverted` or custom

## `warn`

```ab
pub fun warn(message: Text, with_timestamp: Bool = false): Null 
```

Prints a warning message with predefined format

