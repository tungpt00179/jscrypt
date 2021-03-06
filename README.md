**jscrypt**
==
Encrypt/Decrypt your files with percentage progress and desired chunksize via Node.js built-in crypto and stream modules.

jscrypt is a very small and handy module for encrypting/decrypting files with selected speed and a progress callback. 

NEW VERSION: Now It's possible to know when the job is done. Callback will return a boolean type,value of "true" to show the job is done.

>npm install jscrypt --save

-------------------
>**Module functions:**
>var jscrypto = require('jscrypto');
>jscrypto.encryptFile(*sourceFile*,*destinationFile*,*algorithm*,*password*,*chunksize*,*callback*);
>jscrypto.decryptFile(*sourceFile*,*destinationFile*,*algorithm*,*password*,*chunksize*,*callback*);

We assume that we want to encrypt file named "A.txt" with AES256 encryption algorithm, password "P@sW0rD" and by chunksize of 655000 bytes  :

>var jscrypto = require('jscrypto');

>jscrypto.encryptFile("A.txt","A-encrypted.txt","aes256","P@sW0rD",655000,(progress) =>{

>console.log(progress);

>});
>

Now we want to decrypt file named "A-encrypted.txt" :
>var jscrypto = require('jscrypto');

>jscrypto.decryptFile("A-encrypted.txt","A-decrypted.txt","aes256","P@sW0rD",655000,(progress) =>{

>console.log(progress);

>});
>

New version feature: callback returns a boolean when job is done. For example:
>jscrypto.encryptFile("A-encrypted.txt","A-decrypted.txt","aes256","P@sW0rD",655000,(isDone)=>{
    if(isDone === true ) {
        console.log('Job is done!);
    }
});

Notice: default chunksize is 665536. Whenever you prefer to use default chunksize, you should pass 0 to chunksize argument.


>**Supported Algorithms**:
>AES-128-CBC,
AES-128-CBC-HMAC-SHA1,
AES-128-CBC-HMAC-SHA256,
AES-128-CFB,
AES-128-CFB1,
AES-128-CFB8,
AES-128-CTR,
AES-128-ECB,
AES-128-OFB,
AES-128-XTS,
AES-192-CBC,
AES-192-CFB,
AES-192-CFB1,
AES-192-CFB8,
AES-192-CTR,
AES-192-ECB,
AES-192-OFB,
AES-256-CBC,
AES-256-CBC-HMAC-SHA1,
AES-256-CBC-HMAC-SHA256,
AES-256-CFB,
AES-256-CFB1,
AES-256-CFB8,
AES-256-CTR,
AES-256-ECB,
AES-256-OFB,
AES-256-XTS,
AES128 => AES-128-CBC,
AES192 => AES-192-CBC,
AES256 => AES-256-CBC,
BF => BF-CBC,
BF-CBC,
BF-CFB,
BF-ECB,
BF-OFB,
CAMELLIA-128-CBC,
CAMELLIA-128-CFB,
CAMELLIA-128-CFB1,
CAMELLIA-128-CFB8,
CAMELLIA-128-ECB,
CAMELLIA-128-OFB,
CAMELLIA-192-CBC,
CAMELLIA-192-CFB,
CAMELLIA-192-CFB1,
CAMELLIA-192-CFB8,
CAMELLIA-192-ECB,
CAMELLIA-192-OFB,
CAMELLIA-256-CBC,
CAMELLIA-256-CFB,
CAMELLIA-256-CFB1,
CAMELLIA-256-CFB8,
CAMELLIA-256-ECB,
CAMELLIA-256-OFB,
CAMELLIA128 => CAMELLIA-128-CBC,
CAMELLIA192 => CAMELLIA-192-CBC,
CAMELLIA256 => CAMELLIA-256-CBC,
CAST => CAST5-CBC,
CAST-cbc => CAST5-CBC,
CAST5-CBC,
CAST5-CFB,
CAST5-ECB,
CAST5-OFB,
DES => DES-CBC,
DES-CBC,
DES-CFB,
DES-CFB1,
DES-CFB8,
DES-ECB,
DES-EDE,
DES-EDE-CBC,
DES-EDE-CFB,
DES-EDE-OFB,
DES-EDE3,
DES-EDE3-CBC,
DES-EDE3-CFB,
DES-EDE3-CFB1,
DES-EDE3-CFB8,
DES-EDE3-OFB,
DES-OFB,
DES3 => DES-EDE3-CBC,
DESX => DESX-CBC,
DESX-CBC,
IDEA => IDEA-CBC,
IDEA-CBC,
IDEA-CFB,
IDEA-ECB,
IDEA-OFB,
RC2 => RC2-CBC,
RC2-40-CBC,
RC2-64-CBC,
RC2-CBC,
RC2-CFB,
RC2-ECB,
RC2-OFB,
RC4,
RC4-40,
RC4-HMAC-MD5,
SEED => SEED-CBC,
SEED-CBC,
SEED-CFB,
SEED-ECB,
SEED-OFB,
AES-128-CBC,
AES-128-CBC-HMAC-SHA1,
AES-128-CBC-HMAC-SHA256,
id-aes128-CCM,
AES-128-CFB,
AES-128-CFB1,
AES-128-CFB8,
AES-128-CTR,
AES-128-ECB,
id-aes128-GCM,
AES-128-OFB,
AES-128-XTS,
AES-192-CBC,
id-aes192-CCM,
AES-192-CFB,
AES-192-CFB1,
AES-192-CFB8,
AES-192-CTR,
AES-192-ECB,
id-aes192-GCM,
AES-192-OFB,
AES-256-CBC,
AES-256-CBC-HMAC-SHA1,
AES-256-CBC-HMAC-SHA256,
id-aes256-CCM,
AES-256-CFB,
AES-256-CFB1,
AES-256-CFB8,
AES-256-CTR,
AES-256-ECB,
id-aes256-GCM,
AES-256-OFB,
AES-256-XTS,
aes128 => AES-128-CBC,
aes192 => AES-192-CBC,
aes256 => AES-256-CBC,
bf => BF-CBC,
BF-CBC,
BF-CFB,
BF-ECB,
BF-OFB,
blowfish => BF-CBC,
CAMELLIA-128-CBC,
CAMELLIA-128-CFB,
CAMELLIA-128-CFB1,
CAMELLIA-128-CFB8,
CAMELLIA-128-ECB,
CAMELLIA-128-OFB,
CAMELLIA-192-CBC,
CAMELLIA-192-CFB,
CAMELLIA-192-CFB1,
CAMELLIA-192-CFB8,
CAMELLIA-192-ECB,
CAMELLIA-192-OFB,
CAMELLIA-256-CBC,
CAMELLIA-256-CFB,
CAMELLIA-256-CFB1,
CAMELLIA-256-CFB8,
CAMELLIA-256-ECB,
CAMELLIA-256-OFB,
camellia128 => CAMELLIA-128-CBC,
camellia192 => CAMELLIA-192-CBC,
camellia256 => CAMELLIA-256-CBC,
cast => CAST5-CBC,
cast-cbc => CAST5-CBC,
CAST5-CBC,
CAST5-CFB,
CAST5-ECB,
CAST5-OFB,
des => DES-CBC,
DES-CBC,
DES-CFB,
DES-CFB1,
DES-CFB8,
DES-ECB,
DES-EDE,
DES-EDE-CBC,
DES-EDE-CFB,
DES-EDE-OFB,
DES-EDE3,
DES-EDE3-CBC,
DES-EDE3-CFB,
DES-EDE3-CFB1,
DES-EDE3-CFB8,
DES-EDE3-OFB,
DES-OFB,
des3 => DES-EDE3-CBC,
desx => DESX-CBC,
DESX-CBC,
id-aes128-CCM,
id-aes128-GCM,
id-aes128-wrap,
id-aes192-CCM,
id-aes192-GCM,
id-aes192-wrap,
id-aes256-CCM,
id-aes256-GCM,
id-aes256-wrap,
id-smime-alg-CMS3DESwrap,
idea => IDEA-CBC,
IDEA-CBC,
IDEA-CFB,
IDEA-ECB,
IDEA-OFB,
rc2 => RC2-CBC,
RC2-40-CBC,
RC2-64-CBC,
RC2-CBC,
RC2-CFB,
RC2-ECB,
RC2-OFB,
RC4,
RC4-40,
RC4-HMAC-MD5,
seed => SEED-CBC,
SEED-CBC,
SEED-CFB,
SEED-ECB,
SEED-OFB,
