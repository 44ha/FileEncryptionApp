# Encryption App (Python)

Desktop GUI application for encrypting and decrypting text files. Supports two algorithms: Skipjack (symmetric) and Rabin (asymmetric). Built with Tkinter.

## Features

- Encrypt text and save the output to a file
- Decrypt encrypted files with the correct key
- Key generation window for both algorithms
- Security options: expiry time, max decryption attempts, fake password with decoy content
- Terminal-style UI (black background, green text, Consolas font)

## Files

```
main.py                  entry point, main menu, key generation window
encryption_window.py     encrypt/decrypt UI and logic
skipjack_algorithm.py    Skipjack cipher implementation
rabin_algorithm.py       Rabin cryptosystem implementation
security_features.py     expiry, attempt limiting, fake password logic
```

## Requirements

Python 3.8+. No third-party packages — uses only the standard library (`tkinter`, `os`, `sys`).

## Run

```bash
python main.py
```

## Algorithms

**Skipjack** — symmetric block cipher. Same key for encryption and decryption. Key is auto-generated as a 10-byte sequence.

**Rabin** — asymmetric. Encryption uses public key `n = p * q`. Decryption requires private keys `p` and `q`. Security is based on the difficulty of factoring `n`.

## Security options

When encrypting you can optionally set:

- **Expiry** — number of hours before the file can no longer be decrypted
- **Max attempts** — lock the file after N failed decryption attempts  
- **Fake password + content** — a decoy password that shows different (fake) content when used

## How to use

1. Select an algorithm from the dropdown.
2. Click Encrypt or Decrypt.
3. For encryption: paste your text, enter a key, choose an output file, optionally set security options, click Encrypt.
4. For decryption: select the encrypted file, enter the key (or private keys for Rabin), click Decrypt.
5. Use Generate Key to create and save a fresh key for either algorithm.
