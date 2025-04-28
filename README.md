def modify_and_write_file(input_filename, output_filename):
    """
    Reads a file, converts its content to uppercase, and writes it to a new file.
    Handles potential file-related errors.
    """
    try:
        with open(input_filename, 'r') as infile:
            content = infile.read()
    except FileNotFoundError:
        print(f"Error: The file '{input_filename}' was not found.")
        return
    except IOError:
        print(f"Error: Could not read the file '{input_filename}'.")
        return

  modified_content = content.upper()

  try:
        with open(output_filename, 'w') as outfile:
            outfile.write(modified_content)
        print(f"Successfully read '{input_filename}', converted to uppercase, and wrote to '{output_filename}'.")
    except IOError:
        print(f"Error: Could not write to the file '{output_filename}'.")

if __name__ == "__main__":
    input_file = input("Enter the name of the file you want to read: ")
    output_file = input("Enter the name for the new output file: ")
    modify_and_write_file(input_file, output_file)
