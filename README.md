# Domain Email Record Checker

## Project Description

The Domain Email Record Checker is a Go-based tool that reads domain names from the standard input and checks for the presence of MX, SPF, and DMARC records. It performs DNS lookups for each domain and outputs the results in a CSV format, which includes whether the domain has the respective records and their values if they exist. This tool can be useful for administrators and developers who need to verify email-related DNS settings for multiple domains.

## Functions

### main

The `main` function is the entry point of the program. It:

- Initializes a new scanner to read from standard input.
- Prints the CSV header.
- Reads domain names line by line from the standard input.
- Calls the `checkDomain` function for each domain.
- Logs any errors that occur during scanning.

### checkDomain

The `checkDomain` function takes a domain name as input and checks for the presence of MX, SPF, and DMARC records. It:

- Initializes boolean and string variables to store the results.
- Performs a DNS lookup for MX records and updates the `hasMX` variable.
- Performs a DNS lookup for TXT records and updates the `hasSPF` and `spfRecord` variables if an SPF record is found.
- Performs a DNS lookup for TXT records at the `_dmarc.` subdomain and updates the `hasDMARC` and `dmarcRecord` variables if a DMARC record is found.
- Prints the results in CSV format.

## How to Install & Run the Project

### Prerequisites

Ensure you have Go installed on your machine. You can download and install it from the official [Go website](https://golang.org/dl/). 

### Installation

1. Clone the repository or download the source code:

   ```sh
   git clone https://github.com/fkidwai/Email-Record-Checker.git
