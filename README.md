# PKI-Infrastructure

## Description

This project demonstrates the implementation of Public Key Infrastructure (PKI) for secure communication. It shows how digital certificates, public and private keys, and certificate authorities work together to provide authentication, encryption, and data integrity. The project uses OpenSSL to create keys, certificates, and manage PKI components.

## Installation

steps to set up the PKI Infrastructure:
1. Install OpenSSL:
   Download and install OpenSSL on your system.
2. Verify Installation:
   open terminal or command prompt and run:
   openssl version
3. Create Project Folder:
   mkdir pki-project
   cd pki-project

## How to Run

steps below to implement PKI:
1. Generate Root Key
   openssl genrsa -out rootCA.key 2048
2. Create Root Certificate
   openssl req -x509 -new -nodes -key rootCA.key -sha256 -days 365 -out rootCA.crt
3. Generate Server Key
   openssl genrsa -out server.key 2048
4. Create Certificate Signing Request (CSR)
   openssl req -new -key server.key -out server.csr
5. Sign Certificate using Root CA
   opensssl x509 -req -in server.csr -CA rootCA.crt -CAkey rootCA.key -CAcreateserial -out server.crt -days 365 -sha256
6. Verify Certificate
   openssl verify -CAfile rootCA.crt server.crt

## Output 

- Root CA Certificate
- Server Certificate
- Private Keys
- Verified secure communication setup



