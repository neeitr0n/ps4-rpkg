# PS4-rPKG

Remote PKG installer for PlayStation 4.

PS4-rPKG is a local network tool for sending and installing PKG packages from a Linux computer to a PlayStation 4 console. It provides a web interface for selecting packages, managing the installation queue and monitoring file transfers.

## Features

- Select PKG files through a web interface.
- Add and remove packages from the installation queue.
- Enter the PS4 address directly in the web interface.
- Send installation requests to the console through Remote Package Installer (RPI).
- Transfer package files over HTTP and display transfer progress.
- Attempt to start RPI through BinLoader if the RPI service is not already available.
- Installing PS4 games while the console is in Rest Mode. 

## Requirements

- Linux computer running Python 3.
- PlayStation 4 and computer connected to the same local network.
- GoldHEN with a compatible Remote Package Installer (RPI) environment.
- BinLoader enabled on the console if automatic RPI payload loading is needed.
- Tkinter for the file selection dialog.

The Python server uses the standard library and does not require third-party Python packages.

## Running

Clone the repository:

```bash
git clone https://github.com/neeitr0n/ps4-rpkg.git
cd ps4-rpkg
```

Start the server:

```bash
python3 server.py
```

By default, the web server listens on port `8080` on all network interfaces.

Open the interface from a browser on the same network:

```text
http://<PC-IP>:8080
```

Replace `<PC-IP>` with the local IP address of the computer running PS4-rPKG. The console IP address is entered in the web interface; it does not need to be hardcoded in the Python file.

## Usage

1. Start PS4-rPKG on the Linux computer.
2. Open the web interface using the computer's local IP address and port `8080`.
3. Enter the IP address of the PS4.
4. Select the PKG files to install.
5. Start the installation and monitor the transfer progress in the interface.

The computer and console must be able to communicate over the local network. The PS4 does not need direct internet access for a local transfer.

## Network and security

PS4-rPKG is designed for use on a trusted local network. The current HTTP server does not provide authentication and listens on all network interfaces. Do not expose port `8080` to the public internet or to networks you do not trust.

## Development status

PS4-rPKG is an early-stage project. It has been tested with a physical PS4 console, but compatibility may depend on the console firmware, GoldHEN version and RPI environment.

Features, configuration and the web interface may change between releases. Bug reports and contributions are welcome.

## License

No license has been specified yet. Until a license is added, the repository is not explicitly licensed for redistribution or modification.
