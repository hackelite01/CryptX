
# [CryptX - Encryption and Decryption Algorithm](https://cryptx.streamlit.app/)

## Table of Contents

- [Overview](#overview)
- [Installation](#installation)
- [Usage](#usage)
  - [Generating Keys](#generating-keys)
  - [Modifying Messages](#modifying-messages)
  - [Encrypting Messages](#encrypting-messages)
  - [Decrypting Messages](#decrypting-messages)

---

# Overview

This Python script provides functions for key generation, message modification, encryption, and decryption. The algorithm employs a method where each character's ASCII value in the message is modified during encryption and reversed during decryption, ensuring message security.

### Key Features

- **Key Generation:** Generates random public and private keys based on the message length.
- **Message Modification:** Enhances security by adding random letters to the message before encryption.
- **Encryption:** Encrypts the modified message using a simple shift operation on ASCII values.
- **Decryption:** Reverses the encryption process to recover the original message.

### Method
- **Encryption:** Each character's ASCII value is incremented by 2 during encryption.
- **Decryption:** Encrypted ASCII values are decremented by 2 to recover the original message.

### Logic
- **Key Generation:** Generates random keys for encoding and decoding, enhancing security.
- **Message Modification:** Adds and removes random characters to obscure the message, further enhancing security.

### Operations
- **Encryption:** Modifies ASCII values to obfuscate the message.
- **Decryption:** Reverses modifications to recover the original message.

### Functions
- `generate_keys(message)`: Generates random keys for encoding and decoding.
- `add_random_letters(message)`: Adds random characters to obscure the message.
- `encrypt_message(modified_message)`: Encrypts the message by modifying ASCII values.
- `decrypt_message(encrypted_message)`: Decrypts the message by reversing modifications.

## Security
- The algorithm employs random key generation and message modification techniques to enhance security and prevent unauthorized access to messages.

### Complexity

- **Key Generation:** O(1) (constant time complexity)
- **Message Modification:** O(n) (linear time complexity based on message length `n`)
- **Encryption and Decryption:** O(n) (linear time complexity based on message length `n`)

---

# Installation

No special installation is required. Simply ensure you have Python 3.x installed on your system.

---

# Usage

### Generating Keys

The `generate_keys(message)` function generates a random public key and a private key for encryption and decryption. The public key is based on the message length, and the private key is generated using random bytes and encoded in Base64 format.

```python
public_key, private_key = generate_keys(message)
print("Public Key:", public_key)
print("Private Key:", private_key)
```

### Modifying Messages

The `add_random_letters(message)` function adds random printable ASCII characters at the beginning and end of the message. This modification enhances the security of the encryption process by introducing randomness.

```python
modified_message, random_letter = add_random_letters(message)
print("Modified Message:", modified_message)
print("Random Letter:", random_letter)
```

### Encrypting Messages

The `encrypt_message(modified_message)` function encrypts the modified message by shifting each character's ASCII value by 2 (Caesar cipher-like encryption). This operation is reversible and provides basic encryption.

```python
encrypted_message = encrypt_message(modified_message)
print("Encrypted Message:", encrypted_message)
```

### Decrypting Messages

The `decrypt_message(encrypted_message)` function decrypts the encrypted message by reversing the encryption process, i.e., shifting each character's ASCII value back by 2. It also removes the random letters added during encryption to recover the original message.

```python
decrypted_message, original_message = decrypt_message(encrypted_message)
print("Decrypted Message:", decrypted_message)
print("Original Message without Random Letters:", original_message)
```
