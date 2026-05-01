# 🔐 Secure File Encryption and Management Tool

A secure, cross-platform utility to encrypt and decrypt files using **AES-256 in CBC mode**, with integrity verification via **SHA-256 hashing**. Includes both **CLI and GUI interfaces** for flexible use across environments.

---

## 📌 Features

- **AES-256 Encryption/Decryption** using CBC mode
- **SHA-256 Hashing** for data integrity verification
- **Metadata Tracking**: Stores original file info, timestamp, and hash
- **Tamper Detection** upon decryption
- **Two User Interfaces**:
  - Command-line interface (`main.py`)
  - Graphical user interface (`gui.py`)
- Automatic key generation and loading

---

## 🧰 Requirements

Make sure the following are installed:

- Python 3.x
- `cryptography` library
- `PyQt5` (for GUI)

### Install Dependencies

```bash
pip install cryptography PyQt5
```

---
key generation python script:

python3 -c "from cryptography.hazmat.primitives.ciphers.algorithms import AES; import os; key = os.urandom(32); open('secret.key', 'wb').write(key); print('Key generated!')"

## 📁 Project Structure

```
.
├── encryption_utils.py    # Core crypto functions
├── metadata_handler.py    # Metadata storage and lookup
├── main.py                # CLI interface
└── gui.py                 # GUI interface
```

---

## ▶️ Usage

### 🔹 CLI Mode

Run the CLI interface:

```bash
python main.py
```

Select option `1` to encrypt or `2` to decrypt:

- **Encryption**:
  - Enter path of the file to encrypt.
  - Encrypted file will be saved with `.enc` extension.
  - SHA-256 hash and metadata stored automatically.

- **Decryption**:
  - Enter path of the `.enc` file.
  - Decrypted file will be saved with `_decrypted` suffix.
  - Integrity check performed using stored hash.

### 🔹 GUI Mode

Launch the graphical interface:

```bash
python gui.py
```

Use buttons to:
- Encrypt any file (shows encrypted path)
- Decrypt `.enc` files (with tamper detection alert)

---

## 🔐 Security Highlights

- AES-256 with CBC ensures strong symmetric encryption
- Random Initialization Vector (IV) per encryption
- PKCS#7 padding manually implemented for block alignment
- SHA-256 hash used to verify file integrity post-decryption
- Key stored in plaintext file `secret.key` – must be protected

> ⚠️ Note: For production use, implement password-based key derivation and secure key storage.

---

## 📦 Data Storage

- **Key**: Stored in `secret.key` (binary format)
- **Metadata**: Stored in `metadata.db` (JSON format)

---

## 🛠 Future Enhancements

- Add password-based key derivation (e.g., PBKDF2)
- Implement SQLite for structured metadata handling
- Add support for folder encryption and batch processing
- Integrate unit tests and logging system
- Package as standalone executable (e.g., PyInstaller)

---

## ✅ License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

---

## 👤 Author: 
**Mahenazbanu**
