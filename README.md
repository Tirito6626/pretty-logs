# pretty-logs

Tiny, dependency-less, highly customizable Amber library for pretty error/log/warning messages

## Installation

### using amethyst
Add `pretty-logs` to `amethyst.ini`:

```ini
[dependencies]
pretty-logs = https://github.com/Tirito6626/pretty-logs
```

Download the dependency:

```sh
amethyst install
```

Import into your project:

```ab
import * from "../vendor/pretty-logs/src/main.ab"
```

### using git
Clone the repository:

```sh
git clone https://github.com/Tirito6626/pretty-logs
```

Import into your project:

```ab
import * from "/path/to/pretty-logs/src/main.ab"
```


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

## `error_invalid_argument`

```ab
pub fun error_invalid_argument(arguments: [Text], position: Int, correct: Text = ""): Null? 
```

Prints "Invalid Argument" error with marking the invalid argument
`position` is the array index of the invalid argument
If `correct` is supplied, an extra "Did you mean <correct>?" is printed

## `lib_error`

```ab
fun lib_error(message: Text): Null? 
```

## `log`

```ab
pub fun log(message: Text, with_timestamp: Bool = false): Null 
```

Prints a log message with predefined format

## `reload_format`

```ab
pub fun reload_format() 
```

Reloads all formats with `PREFIX_FORMAT`

## `success`

```ab
pub fun success(message: Text, with_timestamp: Bool = false): Null 
```

Prints a success message with predefined format

## `update_error_format`

```ab
pub fun update_error_format(prefix_style: Text, monotone: Bool = false): Null 
```

Supported prefix styles: `default`, `classic`, `minimal`, `inverted` or custom

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

