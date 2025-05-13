# python-week-7a

def modify_content(content):
    """
    Function to modify the content.
    For this example, it converts all text to uppercase.
    """
    return content.upper()

def main():
    # Ask the user for the input filename
    input_file = input("Enter the name of the file to read from: ")

    try:
        # Attempt to open and read the file
        with open(input_file, 'r') as file:
            content = file.read()
        
        # Modify the content
        modified_content = modify_content(content)

        # Define output filename
        output_file = "modified_" + input_file

        # Write the modified content to a new file
        with open(output_file, 'w') as file:
            file.write(modified_content)

        print(f"Success! Modified content has been saved to '{output_file}'.")

    except FileNotFoundError:
        print(f"Error: The file '{input_file}' does not exist.")
    except IOError:
        print(f"Error: Unable to read from or write to file '{input_file}'.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

if __name__ == "__main__":
    main()
