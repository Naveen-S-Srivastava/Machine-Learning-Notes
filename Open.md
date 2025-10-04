# File Handling in Python

## Objective
1. Create and write data to a file in Python
2. Write multiple lines of text to a file using lists and loops
3. Add new information to an already existing file without erasing its content
4. Compare and contrast the different file modes in Python

## Writing to a File

You can create a new text file and write data to it using Python's `open()` function. The `open()` function takes two main arguments: the file path (including the file name) and the mode parameter.

### Basic File Writing Example

```python
# Create a new file Example2.txt for writing
with open('Example2.txt', 'w') as file1:
    file1.write("This is line A\n")
    file1.write("This is line B\n")
    # file1 is automatically closed when the 'with' block exits
```

**Code Explanation:**
- **Line 2:** `with open('Example2.txt', 'w') as file1:`
  - Uses the `open()` function to open/create a file named `Example2.txt` for writing (`'w'` mode)
  - The `'w'` mode specifies we intend to write data to the file
  - The `with` statement ensures the file is automatically closed when the code block exits

- **Line 3:** `file1.write("This is line A\n")`
  - Uses the `write()` method to add text to the file
  - `\n` represents a newline character

- **Line 4:** `file1.write("This is line B\n")`
  - Adds another line of text to the file

## Writing Multiple Lines Using Lists and Loops

You can use a list to store multiple lines of text and write them to a file using a loop.

```python
# List of lines to write to the file
Lines = ["This is line 1", "This is line 2", "This is line 3"]

# Create a new file Example3.txt for writing
with open('Example3.txt', 'w') as file2:
    for line in Lines:
        file2.write(line + "\n")
    # file2 is automatically closed when the 'with' block exits
```

**Code Explanation:**
- **Line 2:** Defines a list called `Lines` containing multiple lines of text
- **Line 5:** Opens `Example3.txt` for writing (`'w'` mode)
- **Line 6-7:** Iterates through each line in the list and writes it to the file with a newline character

## Appending Data to an Existing File

Use the `'a'` mode to append new data to an existing file without overwriting its contents.

```python
# Data to append to the existing file
new_data = "This is line C"

# Open an existing file Example2.txt for appending
with open('Example2.txt', 'a') as file1:
    file1.write(new_data + "\n")
    # file1 is automatically closed when the 'with' block exits
```

**Code Explanation:**
- **Line 2:** Defines the `new_data` variable with text to append
- **Line 5:** Opens `Example2.txt` for appending (`'a'` mode)
- **Line 6:** Appends the new data to the file with a newline character

## Copying Contents Between Files

You can copy contents from one file to another by reading from the source and writing to the destination.

```python
# Open the source file for reading
with open('source.txt', 'r') as source_file:
    # Open the destination file for writing
    with open('destination.txt', 'w') as destination_file:
        # Read lines from the source file and copy them to the destination file
        for line in source_file:
            destination_file.write(line)
    # Destination file is automatically closed when the 'with' block exits
# Source file is automatically closed when the 'with' block exits
```

**Code Explanation:**
- **Line 2:** Opens the source file for reading (`'r'` mode)
- **Line 4:** Opens the destination file for writing (`'w'` mode)
- **Line 6-7:** Iterates through each line in the source file and writes it to the destination file

## File Modes in Python

The following table provides an overview of different file modes, their syntax, and common use cases:

| Mode | Syntax | Description |
|------|--------|-------------|
| 'r' | `'r'` | Read mode. Opens an existing file for reading. Raises an error if the file doesn't exist. |
| 'w' | `'w'` | Write mode. Creates a new file for writing. Overwrites the file if it already exists. |
| 'a' | `'a'` | Append mode. Opens a file for appending data. Creates the file if it doesn't exist. |
| 'x' | `'x'` | Exclusive creation mode. Creates a new file for writing but raises an error if the file already exists. |
| 'rb' | `'rb'` | Read binary mode. Opens an existing binary file for reading. |
| 'wb' | `'wb'` | Write binary mode. Creates a new binary file for writing. |
| 'ab' | `'ab'` | Append binary mode. Opens a binary file for appending data. |
| 'xb' | `'xb'` | Exclusive binary creation mode. Creates a new binary file for writing but raises an error if it already exists. |
| 'rt' | `'rt'` | Read text mode. Opens an existing text file for reading. (Default for text files) |
| 'wt' | `'wt'` | Write text mode. Creates a new text file for writing. (Default for text files) |
| 'at' | `'at'` | Append text mode. Opens a text file for appending data. (Default for text files) |
| 'xt' | `'xt'` | Exclusive text creation mode. Creates a new text file for writing but raises an error if it already exists. |
| 'r+' | `'r+'` | Read and write mode. Opens an existing file for both reading and writing. |
| 'w+' | `'w+'` | Write and read mode. Creates a new file for reading and writing. Overwrites the file if it already exists. |
| 'a+' | `'a+'` | Append and read mode. Opens a file for both appending and reading. Creates the file if it doesn't exist. |
| 'x+' | `'x+'` | Exclusive creation and read/write mode. Creates a new file for reading and writing but raises an error if it already exists. |

## Conclusion

Working with files is a fundamental aspect of programming, and Python provides powerful tools to perform various file operations. This guide covered key concepts and code examples related to file handling in Python, including writing, appending, and copying files.
