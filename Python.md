# Working with Text Files in Python

## 1. Opening a File

```python
file = open("Example1.txt", "r")  # "r" = read mode
# Other modes: "w" (write), "a" (append)
```

## 2. File Attributes

```python
file.name  # Returns file name as string
file.mode  # Returns mode ('r', 'w', etc.)
```

## 3. Reading File Content

```python
content = file.read()       # Reads entire file as one string
line = file.readline()      # Reads one line at a time
lines = file.readlines()    # Reads all lines into a list
```

## 4. Close the File

```python
file.close()  # Always close after reading
```

## 5. Better Way: Use with

```python
with open("Example1.txt", "r") as file:
    content = file.read()
print(content)  # Safe to use outside; file is already closed
```

## 6. Reading Specific Chunks

```python
with open("Example1.txt", "r") as file:
    print(file.read(16))  # Reads first 16 chars
    print(file.read(5))   # Reads next 5 chars
    print(file.read(9))   # Reads next 9 chars
```

## 7. Reading Line by Line with a Loop

```python
with open("Example1.txt", "r") as file:
    for line in file:
        print(line)
```

## 8. Newlines in Output

* `\n` represents a line break in the file

---

# Reading a File with Open()

**Estimated time needed:** 10 minutes

File handling is an essential aspect of programming, and Python provides built-in functions to interact with files. This guide will explore how to use Python's `open` function to read text files (`.txt`).

## Objectives

1. Describe how to use the `open()` and `read()` Python functions to open and read the contents of a text file.
2. Explain how to use the `with` statement in Python.
3. Describe how to use the `readline()` function in Python.
4. Explain how to use the `seek()` function to read specific character(s) in a text file.

## Introduction

Reading text files involves extracting and processing the data stored within them. Text files can have various structures, and how you read them depends on their format.

### Plain text files

* Plain text files contain unformatted text without any specific structure.
* You can read plain text files line by line or load all the content into memory.

## Opening the File

There are two main methods for opening a file.

### 1. Using Python's `open` function

Suppose we have a file named `file.txt`.

Python's `open` function creates a file object and accesses the data within a text file. It takes two primary parameters:

1. **File path:** Filename and directory where the file is located.
2. **Mode:** Specifies purpose: `'r'` for reading, `'w'` for writing, or `'a'` for appending.

```python
# Open the file in read ('r') mode
file = open('file.txt', 'r')
```

### 2. Using `with` statement

Python's `with` statement simplifies file handling and ensures proper closure of files.

```python
# Open the file using 'with' in read ('r') mode
with open('file.txt', 'r') as file:
    # further code
```

The file is automatically closed when the code block inside the `with` statement exits.

### Advantages of `with` statement

* **Automatic resource management:** File is guaranteed to close even if exceptions occur.
* **Cleaner code:** No need to explicitly call `close()`, making code more readable.

## Reading the Entire Content

You can read the entire content of a file using the `read` method, which stores it as a string in a variable.

```python
# Reading and Storing the Entire Content of a File
with open('file.txt', 'r') as file:
    file_stuff = file.read()
    print(file_stuff)
# 'with' automatically closes the file after execution
```
