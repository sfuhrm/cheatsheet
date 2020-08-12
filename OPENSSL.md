### OpenSSL Cheat Sheet

#### Displaying information
* Showing the content of a PEM certificate<br/>
  `openssl x509 -in file.cert.pem -text`
  
* Showing the content of a CSR certificate signing request<br/>
  `openssl req -in file.csr -text -noout`
  
* Showing the certificate of a running SSL server<br/>
  `openssl s_client -showcerts -connect host.fqdn:8443 </dev/null`

#### Calculating message digests
* Calculating md5<br/>
  `openssl md5 FILE`
* Calculating sha-1<br/>
  `openssl sha1 FILE`
* Calculating sha-2-256<br/>
  `openssl sha256 FILE`
* Calculating sha-3-256<br/>
  `openssl sha3-256 FILE`
