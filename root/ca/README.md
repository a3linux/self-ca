CA
================

# Steps to create a new CA

* Modify the openssl.cnf according to your path and requirments.

* Create the root key

'''
openssl genrsa -aes256 -out private/ca.key.pem 4096
chmod 400 private/ca.key.pem
'''

* Create the root certificate

'''
openssl req -config openssl.cnf -key private/ca.key.pem -new -x509 -day 3650 -sha256 -extensions v3_ca -out certs/ca.cert.pem
chmod 400 certs/ca.cert.pem
'''

* Verify root certificate

'''
openssl x509 -noout -text -in certs/ca.cert.pem
'''


# How to sign server and client certificates
