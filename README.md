# Mail Merge Project

The Mail Merge project automates the process of generating personalized letters using input names and a starting letter template.

## Overview

The project reads a list of names from `./Input/Names/invited_names.txt` and generates personalized letters by replacing placeholders in `./Input/Letters/starting_letter.txt`. Each generated letter is then saved in `./Output/Ready_To_File/letter_for_{name}.txt`.

## Project Structure

- **Input/Names/**: Contains `invited_names.txt` with a list of recipient names.
- **Input/Letters/**: Contains `starting_letter.txt` as the template for the letter with `[name]` as the placeholder.
- **Output/Ready_To_File/**: Stores the personalized letters for each recipient.

## Workflow

1. **Read Names**: Reads the list of names from `invited_names.txt`.
2. **Read Template**: Loads the content of `starting_letter.txt`.
3. **Generate Letters**: Iterates through each name, replaces `[name]` in the template with the current name, and creates a new letter file for each recipient.
4. **Save Letters**: Saves each personalized letter in `letter_for_{name}.txt` format in the `Ready_To_File` directory.

## Example Code

```python
with open("./Input/Names/invited_names.txt") as names_file:
    names = names_file.readlines()

with open("./Input/Letters/starting_letter.txt") as letter_file:
    letter_contents = letter_file.read()
    for name in names:
        stripped_name = name.strip()
        new_letter = letter_contents.replace("[name]", stripped_name)
        with open(f"./Output/Ready_To_File/letter_for_{stripped_name}.txt", mode="w") as completed_letter:
            completed_letter.write(new_letter)
```

This Python script demonstrates how to automate the mail merge process using simple file operations and string replacement techniques.

## Requirements

- Python 3.x

## Usage

1. Ensure Python is installed on your system.
2. Place recipient names in `./Input/Names/invited_names.txt`.
3. Create the letter template in `./Input/Letters/starting_letter.txt` with `[name]` as the placeholder.
4. Run the script to generate personalized letters.
5. Check the `./Output/Ready_To_File/` directory for the generated letters.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```
