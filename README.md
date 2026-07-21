# alphabet

Tiny, dependency-less, highly customizable Amber library for pretty error/log/warning messages

## Installation

### using amethyst
Add `alphabet` to `amethyst.ini`:

```ini
[dependencies]
alphabet = https://github.com/Tirito6626/alphabet
```

Download the dependency:

```sh
amethyst install
```

Import into your project:

```ab
import * from "../vendor/alphabet/src/main.ab"

error("Something went wrong")
update_format("inverted");
success("Done");
```

### using git
Clone the repository:

```sh
git clone https://github.com/Tirito6626/alphabet
```

Import into your project:

```ab
import * from "/path/to/alphabet/src/main.ab"

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
- ## `invalid-arg`
  - `position` represents the array index of the invalid argument
  - If `correct` is supplied, an extra "Did you mean [correct]?" is printed
<img width="277" height="99" alt="зображення" src="https://github.com/user-attachments/assets/4f2643f5-3beb-413a-9d76-48bb5994586c" />

- ## `too-few-args`
  - `position` represents the minimum amount of arguments
  - If `correct` is supplied, it shows as a placeholder to one of the missing arguments
<img width="416" height="97" alt="зображення" src="https://github.com/user-attachments/assets/d508d2b2-ec5e-4517-b2e8-b542737739fc" />

- ## `missing-value`
  - `position` represents the array index of the argument
  - If `correct` is supplied, it shows as a value placeholder for the option
<img width="521" height="74" alt="зображення" src="https://github.com/user-attachments/assets/030667a9-4799-4bb6-8999-f7958ec6a0ec" />

- ## `invalid-value`
  - `position` represents the array index of the argument
  - `correct` is mandatory in `<ValueType> <RequiredType>` format, separated by a comma. Arrays are not supported
<img width="521" height="74" alt="зображення" src="https://github.com/user-attachments/assets/f1301c64-c4a3-48dc-aeeb-919be5c7d272" />



**Note: `arguments[0]` is consumed as the script name, use custom name if you're using custom arguments array**

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
