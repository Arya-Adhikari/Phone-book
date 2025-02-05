# Phone Book Application

This is a simple Python-based Phone Book application built using `numpy` and `pandas`. It allows you to add and search for contacts.

## Features

- Add a contact with a name and phone number.
- Search for contacts by name.
- Simple and easy-to-use interface.

## Requirements

- Python 3.x
- pandas
- numpy

To install the required libraries, you can use:
pip install pandas numpy

How to Use
1. Add a Contact
You can add a contact by calling the add_contact(name, phone_number) method. It takes two arguments:

name: The name of the contact.
phone_number: The phone number of the contact.
Example:
phone_book.add_contact("John Doe", "123-456-7890")

2. Search for a Contact
You can search for a contact by calling the search_contact(name) method. It returns the contact if found, or a message indicating that the contact was not found.

Example:
print(phone_book.search_contact("John"))
Example Usage
import numpy as np
import pandas as pd

class PhoneBook:
    def __init__(self):
        # Initialize a DataFrame with empty values
        self.data = pd.DataFrame(columns=["Name", "Phone Number"])

    def add_contact(self, name, phone_number):
        # Add a new contact to the DataFrame
        new_contact = pd.DataFrame([[name, phone_number]], columns=["Name", "Phone Number"])
        self.data = pd.concat([self.data, new_contact], ignore_index=True)

    def search_contact(self, name):
        # Search for contact by name
        contact = self.data[self.data["Name"].str.contains(name, case=False)]
        return contact if not contact.empty else "Contact not found"

# Example usage:
phone_book = PhoneBook()

# Adding contacts
phone_book.add_contact("John Doe", "123-456-7890")
phone_book.add_contact("Jane Smith", "987-654-3210")

# Search for a contact
print(phone_book.search_contact("John"))
print(phone_book.search_contact("Alice"))
Output Example:
pgsql
Copy
              Name    Phone Number
0        John Doe    123-456-7890
   Name    Phone Number
1  Jane Smith  987-654-3210

Contact not found

License
This project is open-source and available under the MIT License.
