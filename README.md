# Automated Subdomain Enumeration Tool

This is a Python-based automated subdomain enumeration tool. It discovers subdomains of a given target domain using a predefined wordlist and DNS resolution.

## Features
- Uses asynchronous requests for fast scanning
- Resolves subdomains using DNS queries
- Saves discovered subdomains to an output file (`output.txt`)
- Simple and easy-to-use CLI interface

## Installation
Ensure you have Python installed, then install the required dependencies:
```bash
pip install aiohttp dnspython argparse
```

## Usage
Run the script with a target domain:
```bash
python subdomain_enum.py example.com
```

## Output
The discovered subdomains will be displayed in the terminal and saved to `output.txt`.

## Disclaimer
This tool is for educational and security research purposes only. Do not use it without proper authorization.

