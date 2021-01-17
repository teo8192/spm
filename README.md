# Simple Password Manager

This is a simple password manager.

*USE AT OWN RISK, CRYPTO IS IMPLEMENTED BY MYSELF*

## Design

The passwords are stored in a Sqlite3 database.
The passwords are encrypted using the `chacha20` cipher, see RFC8439.
The `chacha20` cipher is the variant using a 64 bit nonce.

The key for the encryption is generated based on a password using `pbkdf2`, see RFC8018.
Each password stored has a unique 128 bit salt for `pbkdf2` and a unique nonce for `chacha20`.

Salts and nonces are generated using openssl.

I am unsure of the impact of using the same password into `pbkdf2`, but different salts.
