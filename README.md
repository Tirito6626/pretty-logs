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

error("Something went wrong")
update_format("inverted");
success("Done");
```

### using git
Clone the repository:

```sh
git clone https://github.com/Tirito6626/pretty-logs
```

Import into your project:

```ab
import * from "/path/to/pretty-logs/src/main.ab"

error("Something went wrong")
update_format("inverted");
success("Done");
```

## Standard prefix formats

### default
<img width="153" height="105" alt="зображення" src="https://github.com/user-attachments/assets/04fad0f7-275d-43d9-9f80-f637b40c35b4" />

### inverted
<img width="153" height="105" alt="зображення" src="https://github.com/user-attachments/assets/b3e8efb4-eea5-41a8-885f-a90acf2d96bb" />

### minimal
<img width="153" height="105" alt="зображення" src="https://github.com/user-attachments/assets/0800ee72-283f-4423-a0a4-fd42314ba6dc" />

### classic
<img width="153" height="105" alt="зображення" src="https://github.com/user-attachments/assets/7344ce52-73f7-4251-94d1-a143a6ec3bc8" />



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

## `throw`

```ab
pub fun throw(type: Text, arguments: [Text], position: Int, correct: Text = ""): Null? 
```

Throw a predefined error template

Default types:
- "invalid-arg": "Invalid argument" error
- `position` represents the array index of the invalid argument
- If `correct` is supplied, an extra "Did you mean [correct]?" is printed
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


<img width="328" height="94" alt="зображення" src="https://github.com/user-attachments/assets/eebd864d-1ab7-42c8-b3db-e95ec69765cd" />

## `log`

```ab
pub fun log(message: Text, with_timestamp: Bool = false): Null 
```

Prints a log message with predefined format


## `warn`

```ab
pub fun warn(message: Text, with_timestamp: Bool = false): Null 
```

Prints a warning message with predefined format

## `success`

```ab
pub fun success(message: Text, with_timestamp: Bool = false): Null 
```

Prints a success message with predefined format

## `update_error_format`

```ab
pub fun update_error_format(prefix_style: Text, monotone: Bool = false): Null 
```


## `update_log_format`

```ab
pub fun update_log_format(prefix_style: Text, monotone: Bool = false): Null 
```

## `update_success_format`

```ab
pub fun update_success_format(prefix_style: Text, monotone: Bool = false): Null 
```

## `update_warn_format`

```ab
pub fun update_warn_format(prefix_style: Text, monotone: Bool = false): Null 
```

## `reload_format`

```ab
pub fun reload_format() 
```

Reloads all formats with `PREFIX_FORMAT`


## `lib_error`

```ab
fun lib_error(message: Text): Null? 
```
