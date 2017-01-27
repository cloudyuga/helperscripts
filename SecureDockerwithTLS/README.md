## Self signed SSL certificate generator

###About 
  Scripts are provided by CloudYuga Technology Pvt. Ltd.

### How to use this script?

Step 1: Need to install openssl, git and its dependencies.If alraedy then don't do.
```
root@ubuntu-512mb-blr1-01:~# apt install openssl git
```

Step 2: Cloning a repository from GitHub.
```
root@ubuntu-512mb-blr1-01:~# git clone https://github.com/cloudyuga/helperscripts.git
Cloning into 'helperscripts'...
remote: Counting objects: 36, done.
remote: Compressing objects: 100% (31/31), done.
remote: Total 36 (delta 2), reused 35 (delta 1), pack-reused 0
Unpacking objects: 100% (36/36), done.
Checking connectivity... done.
```
#### For generating TLS certificates.

Step 3: Go to the `helperscripts/SecureDockerwithTLS/` directory
```
root@ubuntu-512mb-blr1-01:~# cd helperscripts/SecureDockerwithTLS/
```
Scripts are shown on that directory, they are already executable file.(Note : Don't chanage the permission)
```
root@ubuntu-512mb-blr1-01:~/helperscripts/SecureDockerwithTLS# ls
dockertls  generatetls  README.md
```
Run a script  generatetls with output argument `-o`

Use `-o` argument for output and `~/certs` dir path were certificate generate or save .
```
root@ubuntu-512mb-blr1-01:~/helperscripts/SecureDockerwithTLS# ./generatetls -o ~/certs
====> Certificate Authority
====> Generating location /root/certs
 ====> Generating CA key
Generating RSA private key, 4096 bit long modulus
.........................................................................................................................................................................................................................................++
................................................................................................................................................++
e is 65537 (0x10001)
 ====> Generating CA
 ====> Generating server key
Generating RSA private key, 4096 bit long modulus
...++
.............................................................................................................................................................................................................................................................++
e is 65537 (0x10001)
 ====> Generating server CSR
 ====> Creating subject alternative name
subjectAltName = IP:139.59.39.36,IP:127.0.0.1
 ====> Signing server CSR with CA
Signature ok
subject=/CN=dockerhost.example.com
Getting CA Private Key
 ====> Generating client key
Generating RSA private key, 4096 bit long modulus
.....................................................................................................................................................................................++
..........................................................................++
e is 65537 (0x10001)
 =====> Generating client CSR
 ===> Creating extended key usage
extendedKeyUsage = clientAuth
 =====> Signing client CSR with CA
Signature ok
subject=/CN=client
Getting CA Private Key
====> Change certificates permission
mode of 'ca-key.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
mode of 'ca.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
mode of 'cert.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
mode of 'key.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
mode of 'server-cert.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
mode of 'server-key.pem' changed from 0644 (rw-r--r--) to 0600 (rw-------)
 ====> Done!
```
Check generated file in `~/certs/ shown like:
```
root@ubuntu-512mb-blr1-01:~/helperscripts/SecureDockerwithTLS# ls ~/certs/
ca-key.pem  ca.pem  ca.srl  cert.pem  extfile_client.conf  extfile.conf  key.pem  server-cert.pem  server-key.pem
```
####For configuring the Docker remote API with TLS 

Step 3:
  