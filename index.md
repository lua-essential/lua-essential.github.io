# Essential Library Wiki

Welcome to the **Essential Library Wiki**! This document provides detailed information about the library's features, functions, and usage.

---

## Table of Contents
1. [Getting Started](#getting-started)
2. [Features Overview](#features-overview)
3. [Function Reference](#function-reference)
    - [Logging](#logging)
    - [Colored Console Output](#colored-console-output)
    - [User Input](#user-input)
    - [Random Utilities](#random-utilities)
    - [Console Management](#console-management)
    - [Timing Utilities](#timing-utilities)
    - [File System Utilities](#file-system-utilities)
    - [Fun Utilities](#fun-utilities)
    - [Base64 Utilities](#base64-utilities)
4. [Examples](#examples)
5. [FAQ](#faq)
6. [Contributing](#contributing)
7. [License](#license)

---

## Getting Started

To use the Essential Library, follow these steps:

1. **Download the library**:
   ```sh
   curl -o essential.lua https://raw.githubusercontent.com/Jannnn13/lua-essential/main/essential.lua
   ```

2. **Place the `essential.lua` file in your project directory**.

3. **Require the library in your Lua script**:
   ```lua
   local et = require("essential")
   ```

---

## Features Overview

The Essential Library provides a wide range of utilities to simplify Lua development:

- **Logging**: Log messages with different levels (`info`, `warn`, `error`) and optional colored output.
- **Colored Console Output**: Print messages in various colors using ANSI escape codes.
- **User Input**: Handle yes/no prompts and general user input easily.
- **Random Utilities**: Generate random booleans and tokens.
- **Console Management**: Clear the console, set the console title, and create typewriter effects.
- **Timing Utilities**: Measure execution time and create delays.
- **File System Utilities**: Read, write, and manage files and directories.
- **Fun Utilities**: Add humor with insults, Rickrolls, and text transformations.
- **Base64 Utilities**: Encode and decode Base64 strings.

---

## Function Reference

### Logging
- **`et.log(type, text)`**  
  Logs a message with the specified type (`info`, `warn`, `error`) and text.
  ```lua
  et.log("info", "This is an informational message.")
  et.log("warn", "This is a warning message.")
  et.log("error", "This is an error message.")
  ```

### Colored Console Output
- **`et.cprint(text, color)`**  
  Prints a message in the specified color. Supported colors:
  - `red`
  - `green`
  - `yellow`
  - `blue`
  - `magenta`
  - `cyan`
  - `white`
  ```lua
  et.cprint("This is a green message.", "green")
  et.cprint("This is a red message.", "red")
  ```

### User Input
- **`et.yesno(question)`**  
  Prompts the user with a yes/no question. Returns `true` for "yes" and `false` for "no".
  ```lua
  if et.yesno("Do you want to continue?") then
      print("You chose to continue!")
  else
      print("You chose to exit!")
  end
  ```

- **`et.input(prompt)`**  
  Prompts the user for input and returns the entered value.
  ```lua
  local name = et.input("What is your name?")
  print("Hello, " .. name .. "!")
  ```

### Random Utilities
- **`et.random.boolean()`**  
  Returns a random boolean value (`true` or `false`).
  ```lua
  if et.random.boolean() then
      print("Random boolean returned true!")
  else
      print("Random boolean returned false!")
  end
  ```

- **`et.random.token(length)`**  
  Generates a random alphanumeric token of the specified length (default: 16).
  ```lua
  local token = et.random.token(16)
  print("Generated token: " .. token)
  ```

### Console Management
- **`et.clear()`**  
  Clears the console.
  ```lua
  et.clear()
  ```

- **`et.set_title(title)`**  
  Sets the console title (if supported by the terminal).
  ```lua
  et.set_title("My Lua Program")
  ```

- **`et.typewriter(text, delay)`**  
  Prints text one character at a time with a delay between each character.
  ```lua
  et.typewriter("This message will appear one character at a time.", 0.1)
  ```

### Timing Utilities
- **`et.wait(seconds)`**  
  Pauses execution for the specified number of seconds.
  ```lua
  et.wait(2) -- Waits for 2 seconds
  ```

- **`et.timer(func)`**  
  Measures the execution time of a function and returns the elapsed time in seconds.
  ```lua
  local time_taken = et.timer(function()
      for i = 1, 10000 do
          -- Simulate some work
      end
  end)
  print("Time taken: " .. time_taken .. " seconds")
  ```

### File System Utilities
- **`et.fs.exists(path)`**  
  Checks if a file or directory exists.
  ```lua
  if et.fs.exists("example.txt") then
      print("File exists!")
  end
  ```

- **`et.fs.read(path)`**  
  Reads the entire content of a file.
  ```lua
  local content = et.fs.read("example.txt")
  print(content)
  ```

- **`et.fs.write(path, content)`**  
  Writes content to a file. Supports both strings and tables (for multiple lines).
  ```lua
  et.fs.write("example.txt", {"Line 1", "Line 2", "Line 3"})
  ```

- **`et.fs.mkdir(path)`**  
  Creates a directory.
  ```lua
  et.fs.mkdir("new_folder")
  ```

### Fun Utilities
- **`et.fun.rickroll()`**  
  Prints the lyrics of "Never Gonna Give You Up" with delays.

- **`et.fun.insult()`**  
  Returns a random humorous insult.
  ```lua
  print(et.fun.insult())
  ```

- **`et.fun.uwuify(text)`**  
  Transforms text into "UwU" style.
  ```lua
  print(et.fun.uwuify("Hello, world!"))
  ```

### Base64 Utilities
- **`et.base64.encode(data)`**  
  Encodes a string into Base64.
  ```lua
  local encoded = et.base64.encode("Hello, World!")
  print(encoded)
  ```

- **`et.base64.decode(data)`**  
  Decodes a Base64 string.
  ```lua
  local decoded = et.base64.decode("SGVsbG8sIFdvcmxkIQ==")
  print(decoded)
  ```

---

## Examples

### Example 1: Logging and User Input
```lua
local et = require("essential")

et.log("info", "Welcome to the program!")
if et.yesno("Do you want to continue?") then
    et.cprint("Great! Let's continue.", "green")
else
    et.cprint("Goodbye!", "red")
    os.exit()
end
```

### Example 2: Typewriter Effect and Timing
```lua
local et = require("essential")

et.typewriter("This message will appear one character at a time.", 0.1)
local time_taken = et.timer(function()
    et.wait(2)
end)
print("Waited for " .. time_taken .. " seconds")
```

---

## FAQ

### 1. What platforms does Essential support?
Essential is written in pure Lua and works on any platform that supports Lua.

### 2. Can I use Essential in my project?
Yes! Essential is licensed under the MIT License, so you can use it in both personal and commercial projects.

### 3. How do I report bugs or suggest features?
Feel free to open an issue on the [GitHub repository](https://github.com/Jannnn13/lua-essential/issues).

---

## Contributing

Contributions are welcome! If you'd like to improve the library or add new features, feel free to submit a pull request.

---

## License

This project is licensed under the MIT License. See the [LICENSE](https://github.com/Jannnn13/lua-essential/blob/main/LICENSE) file for details.