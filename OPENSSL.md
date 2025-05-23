### OpenSSL Cheat Sheet

#### Displaying information
* Showing the content of a PEM certificate<br/>
  `openssl x509 -in file.cert.pem -text`
  
* Showing the content of a CSR certificate signing request<br/>
  `openssl req -in file.csr -text -noout`

* Unpack a P12 PKCS#12 certificate bundle:<br/>
  `openssl pkcs12 -in file.p12 -info`
  
* Showing the certificate of a running SSL server<br/>
  `openssl s_client -showcerts -connect host.fqdn:8443 </dev/null`

#### Certificate signing requests
* Create a CSR with 4096 bits and a config file in UTF8 encoding<br/>
  `openssl req -utf8 -newkey rsa:4096 -keyout private_key.key -out csr_file.csr -config csr.cnf`
* View CSR file<br/>
  `openssl req -text -noout -verify -in csr_file.csr `

#### Calculating message digests
* Calculating md5<br/>
  `openssl md5 FILE`
* Calculating sha-1<br/>
  `openssl sha1 FILE`
* Calculating sha-2-256<br/>
  `openssl sha256 FILE`
* Calculating sha-3-256<br/>
  `openssl sha3-256 FILE`

#### Misc
* Generating a random password with 16 chars<br/>
  `openssl rand -base64 16 |head -c16;echo`
