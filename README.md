# Encryption/Decryption Program

## Project Information

**Project Title:** Substitution Cipher Encryption/Decryption System  
**Student Name:** Zaeem Khan  
**Registration Number:** 25MEI10036  
**Institution:** VIT Bhopal University  
**Course:** Computer Science and Engineering  
**Submitted To:** Professor Sukumar  
**Date:** November 22, 2025

---

## Table of Contents

1. [Introduction](#introduction)
2. [Features](#features)
3. [Technology Stack](#technology-stack)
4. [Installation and Setup](#installation-and-setup)
5. [How to Use](#how-to-use)
6. [Program Workflow](#program-workflow)
7. [Code Structure](#code-structure)
8. [Algorithm and Logic](#algorithm-and-logic)
9. [Screenshots](#screenshots)
10. [Security Considerations](#security-considerations)
11. [Future Enhancements](#future-enhancements)
12. [Conclusion](#conclusion)
13. [References](#references)

---

## Introduction

This project implements a **Substitution Cipher** encryption and decryption system using Python. The program provides a simple yet effective method for encrypting plaintext messages by substituting each character with another character from a randomly shuffled key. The same key is then used to decrypt the encrypted text back to its original form.

The substitution cipher is one of the oldest and simplest encryption techniques, where each character in the plaintext is replaced with a corresponding character from the cipher alphabet. This implementation demonstrates fundamental concepts of cryptography and data security.

---

## Features

- **Encryption:** Converts plaintext into encrypted ciphertext using a randomly generated substitution key
- **Decryption:** Converts encrypted text back to original plaintext using the same key
- **Character Support:** Handles uppercase letters, lowercase letters, digits, and punctuation marks
- **Random Key Generation:** Creates a unique substitution key each time the program runs
- **User-Friendly Interface:** Interactive command-line interface for easy operation
- **Case Preservation:** Maintains the original character set integrity

---

## Technology Stack

- **Programming Language:** Python 3.x
- **Libraries Used:**
  - `random` - For shuffling the character set to create substitution keys
  - `string` - For accessing predefined character sets (letters, digits, punctuation)
- **Development Environment:** Python IDE (VS Code/PyCharm/Jupyter Notebook)

---

## Installation and Setup

### Prerequisites

- Python 3.6 or higher installed on your system
- Basic understanding of command-line operations

### Installation Steps

1. **Clone or Download the Project:**
   ```bash
   git clone <repository-url>
   cd encryption-decryption-program
   ```

2. **Verify Python Installation:**
   ```bash
   python --version
   ```

3. **Run the Program:**
   ```bash
   python Encryption-Decryption-Program.py
   ```

---

## How to Use

1. **Start the Program:**
   - Run the Python script from your terminal or IDE
   - The welcome message will appear

2. **Encryption Process:**
   - Enter the text you want to encrypt when prompted
   - The program will display the encrypted text

3. **Decryption Process:**
   - Enter the encrypted text you want to decrypt
   - The program will display the original decrypted text

### Example Usage:

```
Welcome to the Encryption/Decryption Program!
Enter the text to encrypt: Zaeem Khan
Encrypted text: uA+rn Z@Ab
Enter the text to decrypt: uA+rn Z@Ab
Decrypted text: Zaeem Khan
```

---

## Program Workflow

### Flowchart

![Program Flowchart](image.jpg)

The program follows this workflow:

1. **Initialization:** Create character set and generate random substitution key
2. **User Input:** Accept plaintext from user
3. **Encryption:** Transform plaintext using substitution key
4. **Display Encrypted Text:** Show encrypted result
5. **Decryption Input:** Accept encrypted text from user
6. **Decryption:** Transform encrypted text back to plaintext
7. **Display Decrypted Text:** Show original message

---

## Code Structure

### Class: `Cipher`

The main class that handles all encryption and decryption operations.

#### Method: `__init__(self)`

**Purpose:** Initializes the cipher object with character set and substitution key

**Process:**
- Creates a list of all ASCII letters (uppercase and lowercase)
- Adds digits (0-9)
- Adds punctuation marks
- Creates a copy of this character set
- Shuffles the copy to create a random substitution key

#### Method: `encrypt(self, plaintext)`

**Purpose:** Encrypts the input plaintext

**Parameters:**
- `plaintext` (string): The text to be encrypted

**Returns:**
- Encrypted text (string)

**Logic:**
- Iterates through each character in the plaintext
- Finds the index of the character in the original character set
- Replaces it with the character at the same index in the shuffled key
- Returns the encrypted string

#### Method: `decrypt(self, encrypted_text)`

**Purpose:** Decrypts the input encrypted text

**Parameters:**
- `encrypted_text` (string): The text to be decrypted

**Returns:**
- Decrypted plaintext (string)

**Logic:**
- Iterates through each character in the encrypted text
- Finds the index of the character in the shuffled key
- Replaces it with the character at the same index in the original character set
- Returns the decrypted string

### Function: `main()`

**Purpose:** Main driver function that controls program flow

**Process:**
1. Creates a Cipher object
2. Displays welcome message
3. Takes plaintext input from user
4. Encrypts the plaintext and displays result
5. Takes encrypted text input from user
6. Decrypts the text and displays result

---

## Algorithm and Logic

### Pseudocode

```
ALGORITHM SubstitutionCipher

CLASS Cipher:
    
    METHOD __init__():
        // Initialize character set and substitution key
        chars ← list of (ASCII_LETTERS + DIGITS + PUNCTUATION)
        key ← copy of chars
        SHUFFLE(key)
    END METHOD
    
    METHOD encrypt(plaintext):
        // Encrypt plaintext using substitution
        encrypted_text ← empty string
        FOR each char IN plaintext DO
            IF char IN chars THEN
                index ← FIND_INDEX(char, chars)
                encrypted_char ← key[index]
                APPEND encrypted_char TO encrypted_text
            ELSE
                APPEND char TO encrypted_text
            END IF
        END FOR
        RETURN encrypted_text
    END METHOD
    
    METHOD decrypt(encrypted_text):
        // Decrypt encrypted text by reverse substitution
        decrypted_text ← empty string
        FOR each char IN encrypted_text DO
            IF char IN key THEN
                index ← FIND_INDEX(char, key)
                decrypted_char ← chars[index]
                APPEND decrypted_char TO decrypted_text
            ELSE
                APPEND char TO decrypted_text
            END IF
        END FOR
        RETURN decrypted_text
    END METHOD

END CLASS

FUNCTION main():
    // Main program execution
    cipher ← NEW Cipher()
    PRINT "Welcome to the Encryption/Decryption Program!"
    
    plaintext ← INPUT "Enter the text to encrypt: "
    encrypted ← cipher.encrypt(plaintext)
    PRINT "Encrypted text: " + encrypted
    
    encrypted_input ← INPUT "Enter the text to decrypt: "
    decrypted ← cipher.decrypt(encrypted_input)
    PRINT "Decrypted text: " + decrypted
END FUNCTION

// Program entry point
IF __name__ == "__main__":
    CALL main()
END IF
```

### Time Complexity Analysis

- **Initialization:** O(n log n) where n is the size of character set (due to shuffling)
- **Encryption:** O(m × n) where m is the length of plaintext and n is the size of character set
- **Decryption:** O(m × n) where m is the length of encrypted text

### Space Complexity

- O(n) where n is the size of the character set (for storing chars and key lists)

---

## Screenshots

### Code Implementation

![Code Screenshot](image.jpg)

The screenshot shows the complete implementation of the Cipher class with encryption and decryption methods.

### Program Execution

![Program Output](image.jpg)

The screenshot demonstrates the program in action:
- Input: "Zaeem Khan"
- Encrypted Output: "uA+rn Z@Ab"
- Decrypted Output: "Zaeem Khan"

---

## Security Considerations

### Strengths

1. **Simple Implementation:** Easy to understand and implement
2. **Random Key Generation:** Each execution creates a unique substitution pattern
3. **Character Variety:** Supports letters, digits, and punctuation

### Limitations

1. **Frequency Analysis Vulnerability:** Substitution ciphers can be broken using frequency analysis of letters
2. **Key Management:** The key must be securely shared between sender and receiver
3. **Same Session Limitation:** The key changes with each program execution, making it unsuitable for multi-session communication
4. **No Key Persistence:** Current implementation doesn't save or load keys
5. **Statistical Attacks:** Vulnerable to statistical cryptanalysis methods

### Recommendations for Enhancement

- Implement key persistence mechanism
- Add key export/import functionality
- Consider implementing more secure encryption algorithms (AES, RSA)
- Add file encryption capabilities
- Implement digital signatures for authentication

---

## Future Enhancements

1. **GUI Implementation:** Develop a graphical user interface using Tkinter or PyQt
2. **File Encryption:** Add capability to encrypt and decrypt files
3. **Key Management System:** Implement secure key storage and retrieval
4. **Multiple Cipher Support:** Add support for other cipher techniques (Caesar, Vigenère, etc.)
5. **Network Communication:** Enable encrypted message transmission over networks
6. **Password Protection:** Add password-based encryption for additional security
7. **Batch Processing:** Support encryption/decryption of multiple texts at once
8. **Error Handling:** Implement comprehensive error handling and validation
9. **Logging System:** Add logging for encryption/decryption operations
10. **Unit Testing:** Develop comprehensive test suite for all functionalities

---

## Conclusion

This Substitution Cipher project successfully demonstrates fundamental concepts of cryptography and data security. The program provides a practical implementation of classical encryption techniques using Python programming. While the substitution cipher has known vulnerabilities, it serves as an excellent educational tool for understanding encryption principles and provides a foundation for exploring more advanced cryptographic systems.

The project showcases object-oriented programming concepts, string manipulation, and user interaction in Python. It can be extended with additional features to create a more robust and secure encryption system suitable for real-world applications.

---

## References

1. **Python Documentation:**
   - Official Python String Module: https://docs.python.org/3/library/string.html
   - Official Python Random Module: https://docs.python.org/3/library/random.html

2. **Cryptography Concepts:**
   - Schneier, B. (1996). *Applied Cryptography: Protocols, Algorithms, and Source Code in C*. Wiley.
   - Singh, S. (1999). *The Code Book: The Science of Secrecy from Ancient Egypt to Quantum Cryptography*. Doubleday.

3. **Substitution Cipher:**
   - Classical Cipher Techniques: https://en.wikipedia.org/wiki/Substitution_cipher
   - Introduction to Cryptography (Online Courses and Tutorials)

4. **Python Programming:**
   - McKinney, W. (2017). *Python for Data Analysis*. O'Reilly Media.
   - Lutz, M. (2013). *Learning Python*. O'Reilly Media.

---

## Contact Information

**Student:** Zaeem Khan  
**Registration Number:** 25MEI10036  
**Institution:** VIT Bhopal University  
**Department:** Computer Science and Engineering  
**Supervisor:** Professor Sukumar

---

## License

This project is submitted as an academic assignment for VIT Bhopal University. All rights reserved.

---

**End of README**
