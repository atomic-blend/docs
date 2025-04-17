---
icon: binary-lock
---

# Encryption

## Overview

Atomic Blend supports end-to-end encryption, which means that nor us, your ISP, or any cloud provider can access and read your data.&#x20;

Your data is encrypted securely using a derivation of your password to encrypt a data key, which will be used to encrypt all your data.

A mnemonic key is also generated and encrypt the data key to allow you to recover your data in case you loose your password.



## Concept

```mermaid fullWidth="true"
flowchart TD
    I("generate a salt for user key")
    A[User] --> |Enter password| B("Derive user key from password with Argon2")
    B --> C("Generate a random secret (data key)")
    C --> D("Encrypt data key with user key and salt")
    C --> E("Encrypt data key with backup key and salt")

    F("generate BIP39 mnemonic") --> G("Derive backup key from mnemonic with Argon2")

    H --> E
    G --> E
    I --> D

    H("generate a salt for mnemonic")

    J("Store encrypted keys for backup in database")
    D --> J
    E --> J

```

## Algorithms

* Argon2 to derive password / mnemonic to a key
* AES-GCM, with a 256 bits key&#x20;



## Data models

You can find the details of the models, what's encrypted or not, here : [Models](https://app.gitbook.com/s/dxKeXEgHqpeFIV8n9WBU/models "mention")
