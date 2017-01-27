## Self signed SSL certificate generator

###About 
  Scripts are provided by CloudYuga Technology Pvt. Ltd.

### How to use this script?

Step 1: Need to install openssl, git and its dependencies.

Step 2: Cloning a repository from GitHub.
```
$ git clone https://github.com/cloudyuga/helperscripts.git
Cloning into 'helperscripts'...
remote: Counting objects: 24, done.
remote: Compressing objects: 100% (20/20), done.
remote: Total 24 (delta 0), reused 24 (delta 0), pack-reused 0
Unpacking objects: 100% (24/24), done.
Checking connectivity... done.
```
Step 3: Go to the 'helperscripts/SecureDockerwithTLS/' directory
```
$ cd helperscripts/SecureDockerwithTLS/
$ ls
dockertls  generatetls  README.md
```

```
$ ./generatetls -o ~/certs
====> Certificate Authority
====> Generating location /root/certs
 ====> Generating CA key
Generating RSA private key, 4096 bit long modulus
........................................................................................................................................................................................................++
..++
e is 65537 (0x10001)
 ====> Generating CA
 ====> Generating server key
Generating RSA private key, 4096 bit long modulus
............................++
............................................................................................................................................++
e is 65537 (0x10001)
 ====> Generating server CSR
 ====> Creating subject alternative name
subjectAltName = IP:10.0.2.15,IP:127.0.0.1
 ====> Signing server CSR with CA
Signature ok
subject=/CN=dockerhost.example.com
Getting CA Private Key
 ====> Generating client key
Generating RSA private key, 4096 bit long modulus
.............................................++
.............++
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
