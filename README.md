---

# SSH Honeypot

This project is an SSH server honeypot written in Python. It emulates an SSH service, capturing credentials used in attempted logins. This tool can be used to study and monitor unauthorized access attempts.

## Features

- **Customizable Banners**: Allows the selection or creation of SSH banners to present to connecting clients.
- **RSA Key Management**: Automatically generates an RSA key or uses an existing one.
- **Logging**: Logs all login attempts with timestamps, IP addresses, usernames, and passwords.
- **Multi-Threaded**: Handles multiple simultaneous connections.

## Requirements

- Python 3.x
- `paramiko`
- `pyfiglet` (optional, for banner display)

Install the required Python packages using pip:

```bash
pip install paramiko pyfiglet
```

## Usage

Run the SSH honeypot script:

```bash
python ssh-honeypot.py [options]
```

### Command-Line Options

- `-l`, `--list-banners`: List available banners to use.
- `-b INDEX`, `--banner INDEX`: Specify the banner index to use from the list of available banners.
- `-B STRING`, `--banner-string STRING`: Specify a custom banner to use.
- `-f RSA_FILE`, `--file RSA_FILE`: Specify the RSA key file to use. If not specified, a new one is generated dynamically.
- `-n MAX_NUMBER`, `--number MAX_NUMBER`: Maximum number of connections to listen for (default: 10).
- `-o LOG_FILE`, `--output LOG_FILE`: Specify a log file to append records (default: `./ssh-honeypot.log`).
- `-p PORT`, `--port PORT`: Specify the port to listen on (default: 2222).

### Example

To start the SSH honeypot on port 2222 with a custom banner and log file:

```bash
python ssh-honeypot.py -B "SSH-2.0-OpenSSH_8.0p1 Ubuntu-6ubuntu0.1" -o my_log.log -p 2222
```

### Logging

All connection attempts are logged in the following format:

```
timestamp   IP_address   username   password
```

## Contributions

Contributions are welcome. Please fork the repository and submit a pull request.

## License

This project is licensed under the MIT License.

---
