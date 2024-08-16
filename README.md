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

- **Command Format:**
  ```bash
  ./a.out <input_file_name> <flag> <start_index> <end_index>
- The Resulten file is  stored in the directory  'Assignment1'.
  
## Solution Description

The solution for this problem is implemented in the file `2024202009_A1_q1.cpp`. Below is a summary of how the solution is implemented and how errors are handled:


### Handling Argument Constraints 

- **`<input_file_name>`**: This specifies the file to be read. If the file does not exist, the program is terminate with an appropriate error message indicating that the file could not be found.

- **`<flag>`**: This argument must be either `0` or `1`. Any other value should be reported as an invalid constraint, and the program is terminate with an error message.

- **`<start_index>` and `<end_index>`**:
  - Both arguments must be positive integers.
  - If the indices exceed the file size, the program is terminated with an "indexerror" message with approciate prompt.
  - If either argument contains non-numeric characters, the program is terminated with an "index error."
  - Ensure that the condition `start_index <= end_index` is maintained. If not, the program is terminated with an "invalid argument" error message.

### File Handling

- **Input File**: The file specified by `<input_file_name>` is read only if its path exists. If the file path does not exist, the program should terminate with an appropriate file error message.

- **Output Directory and File**:
  - If the output directory does not exist, it should be created with permission mode `0700`.
  - If a file with the same name already exists in the directory, its content should be overwritten.
  - Any failure in directory creation or file operations should prompt an error message with an adequate reason.

### Handling Large Files

To manage large files efficiently, the file is divided into chunks, each of size 1 MB (1024 * 1024 bytes). The process involves:

- **Chunk Formation**: The file is read in chunks of 1 MB, with each chunk temporarily stored in a buffer.
- **Reversing Content**: The content from each chunk is reversed and then written back to the target file.
- **File Cursor Management**: For operations with `flag 1`, the file cursor is adjusted based on `start_index` and `end_index` by using 'lseek' to ensure the correct sections are processed.

This approach continues until all the required content is written to the target file.

 


