# PyCrypter Documentation

`pycrypter` is a Python library that provides various cryptographic algorithms for encryption and decryption. It includes implementations of classic ciphers like Caesar, Hill, and Enigma, as well as modern encryption techniques like DES, ChaCha20, RC4, RC5, RC6, Salsa20, Triple DES, and Transposition Cipher. The library is designed to be easy to use and extend, making it suitable for both educational purposes and practical applications.

## Table of Contents

- [PyCrypter Documentation](#pycrypter-documentation)
  - [Table of Contents](#table-of-contents)
- [Ciphers](#ciphers)
  - [Binary](#binary)
    - [Methods](#methods)
  - [Caesar Cipher](#caesar-cipher)
    - [Methods](#methods-1)
  - [ChaCha20 Cipher](#chacha20-cipher)
    - [Methods](#methods-2)
  - [DES Cipher](#des-cipher)
    - [Methods](#methods-3)
  - [Enigma Machine](#enigma-machine)
    - [Methods](#methods-4)
  - [Hill Cipher](#hill-cipher)
    - [Methods](#methods-5)
  - [Monoalphabetic Cipher](#monoalphabetic-cipher)
    - [Methods](#methods-6)
  - [Polyalphabetic Cipher](#polyalphabetic-cipher)
    - [Methods](#methods-7)
  - [RC4 Cipher](#rc4-cipher)
    - [Methods](#methods-8)
  - [RC5 Cipher](#rc5-cipher)
    - [Methods](#methods-9)
  - [RC6 Cipher](#rc6-cipher)
    - [Methods](#methods-10)
  - [Salsa20 Cipher](#salsa20-cipher)
    - [Methods](#methods-11)
  - [Transposition Cipher](#transposition-cipher)
    - [Methods](#methods-12)
  - [Triple DES Cipher](#triple-des-cipher)
    - [Methods](#methods-13)
- [Hash](#hash)
  - [MD5 Hash](#md5-hash)
    - [Methods](#methods-14)
  - [Examples](#examples)
    - [Binary Example](#binary-example)
    - [Caesar Example](#caesar-example)
    - [ChaCha20 Example](#chacha20-example)
    - [DES Example](#des-example)
    - [Enigma Machine Example](#enigma-machine-example)
    - [Hill Example](#hill-example)
    - [Monoalphabetic Cipher Example](#monoalphabetic-cipher-example)
    - [Polyalphabetic Example](#polyalphabetic-example)
    - [RC4 Example](#rc4-example)
    - [RC5 Example](#rc5-example)
    - [RC6 Cipher](#rc6-cipher-1)
    - [Salsa20Cipher](#salsa20cipher)
    - [Transposition Cipher Example](#transposition-cipher-example)
    - [Triple DES Cipher Example](#triple-des-cipher-example)
    - [MD5 Hash](#md5-hash-1)

---

# Ciphers

## Binary

The `Binary` class provides static methods for converting text to binary representation and vice versa.

### Methods

- **`text_to_binary(text: str) -> str`**: Converts a text string to its binary representation. Each character is represented as an 8-bit binary number, separated by spaces.
  
  **Parameters**:
  - `text` (str): The text to convert.

  **Returns**:
  - `str`: The binary representation of the text.

- **`binary_to_text(binary: str) -> str`**: Converts a binary string back to text. The binary string should be space-separated bytes.

  **Parameters**:
  - `binary` (str): The binary string to convert.

  **Returns**:
  - `str`: The decoded text.

- **`text_to_binary_file(text: str, file_path: str)`**: Converts text to binary and saves it to a file.

  **Parameters**:
  - `text` (str): The text to convert.
  - `file_path` (str): The file path to save the binary representation.

- **`binary_file_to_text(file_path: str) -> str`**: Reads a binary file and converts it back to text.

  **Parameters**:
  - `file_path` (str): The file path containing the binary representation.

  **Returns**:
  - `str`: The decoded text.

---

## Caesar Cipher

The `CaesarCipher` class implements the classic Caesar cipher, a substitution cipher where each letter in the plaintext is shifted by a fixed number of positions down the alphabet.

### Methods

- **`encrypt_text(text: str, shift: int) -> str`**: Encrypts a text using the Caesar cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `shift` (int): The number of positions to shift each letter.

  **Returns**:
  - `str`: The encrypted text.

- **`decrypt_text(text: str, shift: int) -> str`**: Decrypts a text that was encrypted with the Caesar cipher.

  **Parameters**:
  - `text` (str): The encrypted text.
  - `shift` (int): The number of positions used to encrypt.

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, shift: int, output_file_path: str = None)`**: Encrypts the content of a file using the Caesar cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `shift` (int): The number of positions to shift each letter.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, shift: int, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the Caesar cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `shift` (int): The number of positions used to encrypt.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## ChaCha20 Cipher

The `ChaCha20Cipher` class implements the ChaCha20 stream cipher, a modern encryption algorithm designed by Daniel J. Bernstein. It is widely used in secure communication protocols like TLS 1.3.

### Methods

- **`encrypt(text: str, key: bytes, nonce: bytes = None) -> Tuple[bytes, bytes]`**: Encrypts a text using the ChaCha20 cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce (12 bytes, optional).

  **Returns**:
  - `Tuple[bytes, bytes]`: The encrypted data and the nonce used.

- **`decrypt(encrypted_data: bytes, key: bytes, nonce: bytes) -> str`**: Decrypts data that was encrypted with the ChaCha20 cipher.

  **Parameters**:
  - `encrypted_data` (bytes): The encrypted data.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce used during encryption.

  **Returns**:
  - `str`: The decrypted text.

- **`generate_key() -> bytes`**: Generates a random 32-byte key for ChaCha20.

  **Returns**:
  - `bytes`: A random 32-byte key.

- **`encrypt_file(file_path: str, key: bytes, nonce: bytes = None, output_file_path: str = None)`**: Encrypts the content of a file using ChaCha20 and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce (12 bytes, optional).
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, nonce: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with ChaCha20.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce used during encryption.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## DES Cipher

The `DESCipher` class implements the Data Encryption Standard (DES), a symmetric-key block cipher that uses a 56-bit key.

### Methods

- **`encrypt_des(text: str, key: bytes) -> bytes`**: Encrypts a text using DES in CBC mode.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key (adjusted to 8 bytes).

  **Returns**:
  - `bytes`: The IV concatenated with the encrypted text.

- **`decrypt_des(encrypted_text: bytes, key: bytes) -> str`**: Decrypts data that was encrypted with DES in CBC mode.

  **Parameters**:
  - `encrypted_text` (bytes): The IV + encrypted text.
  - `key` (bytes): The decryption key (adjusted to 8 bytes).

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encrypts the content of a file using DES and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key (adjusted to 8 bytes).
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with DES.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The decryption key (adjusted to 8 bytes).
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## Enigma Machine

The `EnigmaMachine` class simulates the Enigma machine, a historical encryption device used during World War II. It uses a series of rotors to perform polyalphabetic substitution.

### Methods

- **`encrypt_char(char: str) -> str`**: Encrypts a single character using the Enigma machine.

  **Parameters**:
  - `char` (str): The character to encrypt.

  **Returns**:
  - `str`: The encrypted character.

- **`encrypt(text: str) -> str`**: Encrypts a text using the Enigma machine.

  **Parameters**:
  - `text` (str): The text to encrypt.

  **Returns**:
  - `str`: The encrypted text.

- **`encrypt_file(file_path: str, output_file_path: str = None)`**: Encrypts the content of a file using the Enigma machine and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the Enigma machine.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## Hill Cipher

The `HillCipher` class implements the Hill cipher, a polygraphic substitution cipher based on linear algebra. It uses a matrix as the key to encrypt blocks of plaintext letters.

### Methods

- **`encrypt_hill(text: str, key_matrix: List[List[int]]) -> Tuple[str, int]`**: Encrypts a text using the Hill cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key_matrix` (List[List[int]]): The encryption key matrix.

  **Returns**:
  - `Tuple[str, int]`: The encrypted text and the padding count.

- **`decrypt_hill(text: str, key_matrix: List[List[int]], padding_count: int = 0) -> str`**: Decrypts a text that was encrypted with the Hill cipher.

  **Parameters**:
  - `text` (str): The encrypted text.
  - `key_matrix` (List[List[int]]): The decryption key matrix.
  - `padding_count` (int): The number of padding characters added during encryption.

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, key_matrix: List[List[int]], output_file_path: str = None)`**: Encrypts the content of a file using the Hill cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key_matrix` (List[List[int]]): The encryption key matrix.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key_matrix: List[List[int]], padding_count: int = 0, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the Hill cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key_matrix` (List[List[int]]): The decryption key matrix.
  - `padding_count` (int): The number of padding characters added during encryption.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---


## Monoalphabetic Cipher

The `MonoalphabeticCipher` class implements a simple substitution cipher where each letter in the plaintext is replaced by a fixed different letter from the alphabet.

### Methods

- **`generate_substitution_alphabet() -> dict`**: Generates a random substitution alphabet.
  
  **Returns**:
  - `dict`: A dictionary mapping each letter to its substitution.

- **`encrypt_monoalphabetic(text: str, substitution_alphabet: dict) -> str`**: Encrypts a text using the substitution alphabet.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `substitution_alphabet` (dict): The substitution alphabet to use.

  **Returns**:
  - `str`: The encrypted text.

- **`decrypt_monoalphabetic(text: str, substitution_alphabet: dict) -> str`**: Decrypts a text using the substitution alphabet.

  **Parameters**:
  - `text` (str): The text to decrypt.
  - `substitution_alphabet` (dict): The substitution alphabet used for encryption.

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, substitution_alphabet: dict, output_file_path: str = None)`**: Encrypts the content of a file using the monoalphabetic cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `substitution_alphabet` (dict): The substitution alphabet to use.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, substitution_alphabet: dict, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the monoalphabetic cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `substitution_alphabet` (dict): The substitution alphabet used for encryption.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## Polyalphabetic Cipher

The `PolyalphabeticCipher` class implements the Vigenère cipher, a method of encrypting alphabetic text by using a simple form of polyalphabetic substitution.

### Methods

- **`encrypt_polyalphabetic(text: str, key: str) -> str`**: Encrypts a text using the Vigenère cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (str): The encryption key.

  **Returns**:
  - `str`: The encrypted text.

- **`decrypt_polyalphabetic(text: str, key: str) -> str`**: Decrypts a text that was encrypted with the Vigenère cipher.

  **Parameters**:
  - `text` (str): The encrypted text.
  - `key` (str): The encryption key used.

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, key: str, output_file_path: str = None)`**: Encrypts the content of a file using the Vigenère cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (str): The encryption key.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: str, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the Vigenère cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (str): The encryption key used.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## RC4 Cipher

The `RC4Cipher` class implements the RC4 stream cipher, a widely used but now considered insecure encryption algorithm.

### Methods

- **`encrypt_rc4(text: str, key: bytes) -> bytes`**: Encrypts a text using the RC4 cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key.

  **Returns**:
  - `bytes`: The encrypted data.

- **`decrypt_rc4(encrypted_text: bytes, key: bytes) -> str`**: Decrypts data that was encrypted with the RC4 cipher.

  **Parameters**:
  - `encrypted_text` (bytes): The encrypted data.
  - `key` (bytes): The encryption key used.

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encrypts the content of a file using the RC4 cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the RC4 cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The encryption key used.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## RC5 Cipher

The `RC5Cipher` class implements the RC5 block cipher, a symmetric-key algorithm designed by Ronald Rivest.

### Methods

- **`encrypt_rc5(text: str, key: bytes) -> bytes`**: Encrypts a text using the RC5 cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key.

  **Returns**:
  - `bytes`: The encrypted data.

- **`decrypt_rc5(encrypted_data: bytes, key: bytes) -> str`**: Decrypts data that was encrypted with the RC5 cipher.

  **Parameters**:
  - `encrypted_data` (bytes): The encrypted data.
  - `key` (bytes): The encryption key used.

  **Returns**:
  - `str`: The decrypted text.

- **`generate_key(size: int = 16) -> bytes`**: Generates a random key for RC5.

  **Parameters**:
  - `size` (int): The size of the key in bytes (default is 16).

  **Returns**:
  - `bytes`: A random key.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encrypts the content of a file using the RC5 cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the RC5 cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The encryption key used.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## RC6 Cipher

The `RC6Cipher` class implements the RC6 block cipher, a more advanced version of RC5.

### Methods

- **`encrypt_rc6(text: str, key: bytes) -> bytes`**: Encrypts a text using the RC6 cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key.

  **Returns**:
  - `bytes`: The encrypted data.

- **`decrypt_rc6(encrypted_data: bytes, key: bytes) -> str`**: Decrypts data that was encrypted with the RC6 cipher.

  **Parameters**:
  - `encrypted_data` (bytes): The encrypted data.
  - `key` (bytes): The encryption key used.

  **Returns**:
  - `str`: The decrypted text.

- **`generate_key(size: int = 16) -> bytes`**: Generates a random key for RC6.

  **Parameters**:
  - `size` (int): The size of the key in bytes (default is 16).

  **Returns**:
  - `bytes`: A random key.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encrypts the content of a file using the RC6 cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the RC6 cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The encryption key used.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## Salsa20 Cipher

The `Salsa20Cipher` class implements the Salsa20 stream cipher, a modern encryption algorithm designed by Daniel J. Bernstein.

### Methods

- **`encrypt(text: str, key: bytes, nonce: bytes = None) -> Tuple[bytes, bytes]`**: Encrypts a text using the Salsa20 cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce (8 bytes, optional).

  **Returns**:
  - `Tuple[bytes, bytes]`: The encrypted data and the nonce used.

- **`decrypt(encrypted_data: bytes, key: bytes, nonce: bytes) -> str`**: Decrypts data that was encrypted with the Salsa20 cipher.

  **Parameters**:
  - `encrypted_data` (bytes): The encrypted data.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce used during encryption.

  **Returns**:
  - `str`: The decrypted text.

- **`generate_key() -> bytes`**: Generates a random 32-byte key for Salsa20.

  **Returns**:
  - `bytes`: A random 32-byte key.

- **`encrypt_file(file_path: str, key: bytes, nonce: bytes = None, output_file_path: str = None)`**: Encrypts the content of a file using Salsa20 and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce (8 bytes, optional).
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, nonce: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with Salsa20.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The encryption key (32 bytes).
  - `nonce` (bytes): The nonce used during encryption.
  - `output_file_path` (str): The path to save the decrypted file (optional).
  
## Transposition Cipher

The `TranspositionCipher` class implements the Rail Fence cipher, a form of transposition cipher that rearranges the plaintext letters by writing them in a zigzag pattern along a number of rails.

### Methods

- **`encrypt_transposition(text: str, rails: int) -> str`**: Encrypts a text using the Rail Fence cipher.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `rails` (int): The number of rails to use (must be >= 2).

  **Returns**:
  - `str`: The encrypted text.

- **`decrypt_transposition(text: str, rails: int) -> str`**: Decrypts a text that was encrypted using the Rail Fence cipher.

  **Parameters**:
  - `text` (str): The encrypted text.
  - `rails` (int): The number of rails used in encryption (must be >= 2).

  **Returns**:
  - `str`: The decrypted text.

- **`encrypt_file(file_path: str, rails: int, output_file_path: str = None)`**: Encrypts the content of a file using the Rail Fence cipher and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `rails` (int): The number of rails to use.
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, rails: int, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with the Rail Fence cipher.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `rails` (int): The number of rails used in encryption.
  - `output_file_path` (str): The path to save the decrypted file (optional).

---

## Triple DES Cipher

The `TripleDESCipher` class implements the Triple DES (3DES) encryption algorithm, which applies the DES algorithm three times to each block of data using two or three different keys, providing a higher level of security than standard DES.

### Methods

- **`generate_key() -> bytes`**: Generates a random valid 24-byte key for Triple DES.

  **Returns**:
  - `bytes`: A 24-byte key suitable for Triple DES.

- **`encrypt_des3(text: str, key: bytes) -> bytes`**: Encrypts a text using Triple DES in CBC mode.

  **Parameters**:
  - `text` (str): The text to encrypt.
  - `key` (bytes): The encryption key (16 or 24 bytes).

  **Returns**:
  - `bytes`: The IV concatenated with the encrypted text.

- **`decrypt_des3(encrypted_data: bytes, key: bytes) -> str`**: Decrypts data that was encrypted with Triple DES.

  **Parameters**:
  - `encrypted_data` (bytes): The IV + encrypted data.
  - `key` (bytes): The decryption key (16 or 24 bytes).

  **Returns**:
  - `str`: The decrypted text.

- **`validate_key(key: bytes) -> bool`**: Validates if a key is suitable for use with Triple DES.

  **Parameters**:
  - `key` (bytes): The key to validate.

  **Returns**:
  - `bool`: `True` if the key is valid, `False` otherwise.

- **`encrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Encrypts the content of a file using Triple DES and saves it to another file.

  **Parameters**:
  - `file_path` (str): The path to the file to encrypt.
  - `key` (bytes): The encryption key (16 or 24 bytes).
  - `output_file_path` (str): The path to save the encrypted file (optional).

- **`decrypt_file(file_path: str, key: bytes, output_file_path: str = None)`**: Decrypts the content of a file that was encrypted with Triple DES.

  **Parameters**:
  - `file_path` (str): The path to the encrypted file.
  - `key` (bytes): The decryption key (16 or 24 bytes).
  - `output_file_path` (str): The path to save the decrypted file (optional).
  
# Hash

## MD5 Hash

The `MD5Hash` class implements the MD5 hashing algorithm, which produces a 128-bit hash value. Although MD5 is no longer considered secure for cryptographic purposes, it is still widely used for data integrity verification.

### Methods

- **`hash(message: str) -> str`**: Computes the MD5 hash of a message.

  **Parameters**:
  - `message` (str): The message to hash.

  **Returns**:
  - `str`: The MD5 hash as a hexadecimal string.

- **`hash_file(file_path: str) -> str`**: Computes the MD5 hash of a file.

  **Parameters**:
  - `file_path` (str): The path to the file to hash.

  **Returns**:
  - `str`: The MD5 hash of the file as a hexadecimal string.

---

## Examples

### Binary Example

```python
from pycrypter.Ciphers import Binary

binary_text = Binary.text_to_binary("Hello")
print(binary_text)  # Output: "01001000 01100101 01101100 01101100 01101111"

text = Binary.binary_to_text("01001000 01100101 01101100 01101100 01101111")
print(text)  # Output: "Hello"
```

### Caesar Example

```python
from pycrypter.Ciphers import CaesarCipher

encrypted = CaesarCipher.encrypt_text("Hello", 3)
print(encrypted)  # Output: "Khoor"

decrypted = CaesarCipher.decrypt_text("Khoor", 3)
print(decrypted)  # Output: "Hello"
```

### ChaCha20 Example

```python
from pycrypter.Ciphers import ChaCha20Cipher

key = ChaCha20Cipher.generate_key()
encrypted, nonce = ChaCha20Cipher.encrypt("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = ChaCha20Cipher.decrypt(encrypted, key, nonce)
print(decrypted)  # Output: "Hello"
```

### DES Example

```python
from pycrypter.Cipher import DESCipher

key = b'mykey123'
encrypted = DESCipher.encrypt_des("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = DESCipher.decrypt_des(encrypted, key)
print(decrypted)  # Output: "Hello"
```

### Enigma Machine Example

```python
from pycrypter.Ciphers import EnigmaMachine

rotor_configs = [
    {'wiring': 'EKMFLGDQVZNTOWYHXUSPAIBRCJ', 'notch': 'Q'},  # Rotor I
    {'wiring': 'AJDKSIRUXBLHWTMCQGZNPYFVOE', 'notch': 'E'},  # Rotor II
    {'wiring': 'BDFHJLCPRTXVZNYEIWGAKMUSQO', 'notch': 'V'}   # Rotor III
]
reflector = {'A': 'Y', 'B': 'R', 'C': 'U', 'D': 'H', 'E': 'Q', 'F': 'S', 'G': 'L',
             'H': 'D', 'I': 'P', 'J': 'X', 'K': 'N', 'L': 'G', 'M': 'O', 'N': 'K',
             'O': 'M', 'P': 'I', 'Q': 'E', 'R': 'B', 'S': 'F', 'T': 'Z', 'U': 'C',
             'V': 'W', 'W': 'V', 'X': 'J', 'Y': 'A', 'Z': 'T'}

enigma = EnigmaMachine(rotor_configs, reflector, [1, 1, 1], ['A', 'A', 'A'])
encrypted = enigma.encrypt("HELLO")
print(encrypted)  # Output: Encrypted text
```

### Hill Example

```python
from pycrypter import HillCipher

key_matrix = [[6, 24, 1], [13, 16, 10], [20, 17, 15]]
encrypted, padding = HillCipher.encrypt_hill("HELLO", key_matrix)
print(encrypted)  # Output: Encrypted text

decrypted = HillCipher.decrypt_hill(encrypted, key_matrix, padding)
print(decrypted)  # Output: "HELLO"
```

### Monoalphabetic Cipher Example

```python
from pycrypter.Ciphers import MonoalphabeticCipher

substitution_alphabet = MonoalphabeticCipher.generate_substitution_alphabet()
encrypted = MonoalphabeticCipher.encrypt_monoalphabetic("Hello", substitution_alphabet)
print(encrypted)  # Output: Encrypted text

decrypted = MonoalphabeticCipher.decrypt_monoalphabetic(encrypted, substitution_alphabet)
print(decrypted)  # Output: "Hello
```

### Polyalphabetic Example

```python
from pycrypter.Ciphers import PolyalphabeticCipher

encrypted = PolyalphabeticCipher.encrypt_polyalphabetic("Hello", "key")
print(encrypted)  # Output: Encrypted text

decrypted = PolyalphabeticCipher.decrypt_polyalphabetic(encrypted, "key")
print(decrypted)  # Output: "Hello"
```

### RC4 Example

```python
from pycrypter.Ciphers import RC4Cipher

key = b'mykey123'
encrypted = RC4Cipher.encrypt_rc4("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = RC4Cipher.decrypt_rc4(encrypted, key)
print(decrypted)  # Output: "Hello"
```

### RC5 Example

```python
from pycrypter.Ciphers import RC5Cipher

key = RC5Cipher.generate_key()
encrypted = RC5Cipher.encrypt_rc5("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = RC5Cipher.decrypt_rc5(encrypted, key)
print(decrypted)  # Output: "Hello"
```

### RC6 Cipher

```python
from pycrypter.Ciphers import RC6Cipher

key = RC6Cipher.generate_key()
encrypted = RC6Cipher.encrypt_rc6("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = RC6Cipher.decrypt_rc6(encrypted, key)
print(decrypted)  # Output: "Hello"
```

### Salsa20Cipher

```python
from pycrypter.Ciphers import Salsa20Cipher

key = Salsa20Cipher.generate_key()
encrypted, nonce = Salsa20Cipher.encrypt("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = Salsa20Cipher.decrypt(encrypted, key, nonce)
print(decrypted)  # Output: "Hello"
```


### Transposition Cipher Example

```python
from pycrypter.Ciphers import TranspositionCipher

encrypted = TranspositionCipher.encrypt_transposition("HELLOWORLD", 3)
print(encrypted)  # Output: "HOLELWRDLO"

decrypted = TranspositionCipher.decrypt_transposition("HOLELWRDLO", 3)
print(decrypted)  # Output: "HELLOWORLD"
```

### Triple DES Cipher Example

```python
from pycrypter.Ciphers import TripleDESCipher

key = TripleDESCipher.generate_key()
encrypted = TripleDESCipher.encrypt_des3("Hello", key)
print(encrypted)  # Output: Encrypted bytes

decrypted = TripleDESCipher.decrypt_des3(encrypted, key)
print(decrypted)  # Output: "Hello"
```

### MD5 Hash

```python
from pycrypter import MD5Hash

# Hash a message
message_hash = MD5Hash.hash("Hello, World!")
print(message_hash)  # Output: MD5 hash of "Hello, World!"

# Hash a file
file_hash = MD5Hash.hash_file("example.txt")
print(file_hash)  # Output: MD5 hash of the file content
```



