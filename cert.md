1. Generate rsa key

openssl genrsa -out ca.key 2048

2. generate csr

openssl req -new -key ca.key -subj "/CN=KUBERNETES-CA" -out ca.csr

3. generate cert

openssl x509 -req -in ca.csr -signkey ca.key -CAcreateserial -out ca.crt -days 1000


