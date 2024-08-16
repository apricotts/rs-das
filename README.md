# CS3.304 - Advanced Operating Systems  Assignment - 1

### Basic Setup and Usage
- Ensure you have the necessary C++ development tools installed.
- It is recommended to use `g++` for compiling C++ programs.
- Use the `g++` compiler to compile your C++ program.
  - Example command to compile:
    ```bash
    g++ -o program_name source_file.cpp
    ```
    - Replace `program_name` with your desired executable name.
    - Replace `source_file.cpp` with your C++ source file.

  - Or 
    ```bash
    g++ <filename>.cpp
    ```
    - Replace `<filename>` with your actual file name.

- Execute the compiled program by running:
  ```bash
  ./program_name

## Q.1 Problem Description

The program performs different file manipulations based on the provided flag value:
- **Flag 0**: Reverses the entire file content.
- **Flag 1**: Reverses the content of specific sections of the file, with the following operations:
  - Reverse content from the start of the file to a specified index.
  - Print the content between two specified indices.
  - Reverse the content from a specified index to the end of the file.
 
## Solution Description

The solution for this problem is implemented in the file `2024202009_A1_q1.cpp`. Below is a summary of how the solution is implemented and how errors are handled:


