# Certification

## Private Key
Must keep secret
- key.pem

## Public Key
To verify but not replicate
- certificate.pem 

## Generate a CSR from an Existing Private Key
```
openssl req -key domain.key -new -out domain.csr
```

## To generate Private and Public Key
```
openssl req -newkey rsa:2048 -nodes -keyout domain.key -x509 -days 365 -out domain.crt
openssl req -newkey rsa:2048 -nodes -keyout key.pem -x509 -days 365 -out certificate.pem
```

## Generate a CSR from an Existing Certificate and Private Key
```
openssl x509 -in domain.crt -signkey domain.key -x509toreq -out domain.csr
```

## Generate a Self-Signed Certificate from an Existing Private Key
```
openssl req -key domain.key -new -x509 -days 365 -out domain.crt
```

## To generate CRT
```
openssl req -newkey rsa:2048 -keyout PRIVATEKEY.key -out MYCSR.csr
```

## Generate a Self-Signed Certificate from an existing private key and CSR
```
openssl x509 -signkey PRIVATEKEY.key -in MYCSR.csr -req -days 365 -out domain.crt
```