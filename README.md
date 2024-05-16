# imphash_generator
generated imphash by IAT table.


Explanation of each aspect of the script:

Function: resolve_ordinals:

This function resolves ordinals to function names when they appear in the import table.
Function: extract_imports:

This function takes a file path (file_path) as input and extracts the imports from the binary file (.exe).
It uses pefile.PE to parse the PE file format.
It iterates through the DIRECTORY_ENTRY_IMPORT of the PE file and extracts the imported module names and their functions.
It converts both DLL names and function names to lowercase and removes file extensions from imported module names.
It returns a list of tuples, where each tuple contains the lowercased module name and a list of its lowercased functions.
Function: generate_md5:

This function generates the MD5 hash of the ordered list of lowercased DLL names and function names.
It sorts the ordered list of strings in lexicographical order.
It generates the MD5 hash of the concatenated ordered list.
It returns the MD5 hash.
Function: main:

This function serves as the entry point of the script.
It calls the extract_imports function to extract the imports from the binary file.
It calls the generate_md5 function to generate the MD5 hash of the imports.
It returns the MD5 hash.
Script Execution:

The script defines the file path for the binary file (file_path).
It calls the main function to execute the script.
It prints the MD5 hash generated from the imports.
