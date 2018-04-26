# Cryptonic V1.3

<p>Basicly Encrypt your messages, files and folders.</p>

# Recommendations

<p>i shouldn't encrypt if file size greater than ram </p>
<p>divide parts big files if file size greater than ram</p>
<p>if you wanna calculate bruteforce chocies. this is formula 255^n - n=patternsize<=>byte
<p>this program now baby so i waiting reviews</p>
<p>Only those who know the pattern key can decrypt the password</p>
<p>Good Decrypting.</p>

# Console commands for Cryptonic.

```
pattern
  set - set patterns for encoding,decoding.(cache from import)
    create - create a pattern of the desired length
Argument-Input - pattern length(Integer)
    ctonfile
Argument-Input - cton Filename(String)
    getfile - creating pattern with according any file
Argument-Input - Filename(String)
    seton - setting pattern with entered key
Argument-Input - Pattern-base64(String)
  get - Getting pattern information
    key - If greater than 5 KB does not print
Console-Output - Pattern-base64(String)
    size - Pattern key size
Console-Output - Pattern-size(String)
    md5 - Returns pattern md5
Console-Output - Pattern-MD5-Hexdigest(String)
    info - Returns pattern md5 and size
Console-Output - Pattern-info(String)
  save - Saves last loaded pattern as file
Argument-Input - Filename(String)
encode - Encoding with last loaded pattern
  text - Encoding simple text
Argument-Input - Text(String)
  file - Encoding file with entered file path
Argument-Input - Filename(String)
  allpath - Encoding all files and folders with entered folder path
Argument-Input - Folder Path(String)
decode - Decoding with last loaded pattern
  text - Decoding simple crypted text(needs pattern key on used to encoding for decoding)
Argument-Input - Encrypted text(String) 
  file - Decoding file with entered file path(needs pattern key on used to encoding for decoding)
Argument-Input -  Filename(String)
  allpath - Decoding crypted all files and folders with entered file path(needs pattern key on used to encoding for decoding)
Argument-Input - Folder path(String)
cry - Compressing paths
  compress - Compressing all paths and files with entered file path
Argument-Input - Folder path(String)
Console-Input - Filename for keeping files and folders(String)
  decompress - Decompressing all paths and files with entered compress file name
Argument-Input - Filename for decompressing files and folders(String)
 ```
 
<h1> Examples for Cryptonic Console</h1>
<h3>Creating patterns</h3>
<h4>Creating 1024 bytes pattern</h4>

```
Cryptonic > pattern set create 1024
Successfully Loaded at cache
```

<h4>Importing pattern with cton file in cache</h4>
<p>Name of pattern file 'test.cton'</p>

```
Cryptonic > pattern set ctonfile test
Successfully Loaded at cache
```

<h4>Creating pattern with according any file</h4>

```
Cryptonic > pattern set getfile test.exe
Successfuly created pattern with test.exe. Loaded at cache
```

```
Cryptonic > pattern set getfile image.png
Successfuly created pattern with image.png. Loaded at cache```
```

<h4>Pattern loading on console program</h4>

```
Cryptonic > pattern set seton T4k3ZNiStqEUurmeX0H1Aw==
Successfully Loaded at cache
```

<h3>Getting Pattern informations</h3>
<h4>Getting pattern key</h4>

```
Cryptonic > pattern get key
-----BEGIN CRYPTONIC KEY-----
VDRrM1pOaVN0cUVVdXJtZVgwSDFBdz09
-----END CRYPTONIC KEY-----
```

<h4>Getting pattern key</h4>

```
Cryptonic > pattern get key
-----BEGIN CRYPTONIC KEY-----
VDRrM1pOaVN0cUVVdXJtZVgwSDFBdz09
-----END CRYPTONIC KEY-----
```

<h5>If greater than 5KB</h5>

```
Cryptonic > pattern set create 6096
Successfully Loaded at cache
Cryptonic > pattern get key
Pattern size bigger than 5KB so didn't print.
```

<h4>Getting pattern size</h4>

```
Cryptonic > pattern get size
Pattern Size : 6096 Byte
```

<h4>Getting pattern md5</h4>

```
Cryptonic > pattern get md5
Pattern MD5 Hash : 6a67bf75891f5f89cc79c082dec56ef3
```

<h4>Getting pattern information</h4>

```
Cryptonic > pattern get info
Pattern Size : 6096 Byte
Pattern MD5 Hash : 6a67bf75891f5f89cc79c082dec56ef3
```

<h3>Encrypt examples</h3>
<h4>Text Encrypting</h4>

```
Cryptonic > encode text "Hello world!"
```

<h4>File Encrypting</h4>

```
Cryptonic > encode file testfile.exe
#Or
Cryptonic > encode file C:/testfile.exe
```

```
Cryptonic > encode file testfile.png
#Or
Cryptonic > encode file C:/testfile.png
```

```
Cryptonic > encode file testfile.doc
#Or
Cryptonic > encode file C:/testfile.doc
```

```
Cryptonic > encode file testfile.bmp
#Or
Cryptonic > encode file C:/testfile.bmp
```

<p> Or something </p>
<h4>Path Encrypting.</h4>

```
Cryptonic > encode allpath "important files/veryimportanttttt"
#Or
Cryptonic > encode allpath "C:/Users/test/important files/veryimportanttttt"
```

<h3>Decrypt examples</h3>
<h4>Text Decrypting.</h4>

```
Crpytonic > decode text dVFmWjhRdDM=
```
<h4>File Decrypting.</h4>

```
Crpytonic > decrypt file testfile.exe.cryptonicted
```
<h4>Path Decrypting.</h4>

```
Crpytonic > decrypt allpath important files/veryimportanttttt-cryptonicted
Crpytonic > decrypt allpath C:/Users/test/important files/veryimportanttttt-cryptonicted
```
<h3>Compress examples</h3>
<h4>Compressing</h4>

```
Cryptonic > cry compress myfolders/myfolder
#OR
Cryptonic > cry compress C:/test/myfolders/myfolder
Please enter file name > example.desired_extends
```
<h4>Decompressing</h4>

```
Cryptonic > cry decompress example.desired_extends
```

# Simple Class Using on Python
<h2>Creating pattern key</h2>

```python
from cryptonic import *
myPatternLen = 1024 # 1024 bytes
patternKey = createCryptonicKey(myPatternLen)
```
<h2>Building Class</h2>

```python
from cryptonic import *
#Pattern creating
myPatternLen = 1024 # 1024 bytes
patternKey = createCryptonicKey(myPatternLen)
#Class building
myCrypter = cryptonic(pattern=patternKey) #Or myCrypter = cryptonic(cryptonicLen=1024) Or myCrypter = cryptonic(patternFilename="test.cton")
```
<h2>Encrypt</h2>

```python
from cryptonic import *
#Pattern creating
myPatternLen = 1024 # 1024 bytes
patternKey = createCryptonicKey(myPatternLen)
#Class building
myCrypter = cryptonic(pattern=patternKey) #Or myCrypter = cryptonic(cryptonicLen=1024) Or myCrypter = cryptonic(patternFilename="test.cton")
#Encrypting
encryptedMessage = myCrypter.encode(data="Hello world!") # Returns Tuple (isSuccess,EncryptedText)
if(encryptedMessage[0]):
    print "Encrypted message : %s"%(encryptedMessage[1])
else:
    print "Encrypt failed."
```
<h3>Output</h3>

```
Encrypted message : ckwvN2ZMMTBpQVFaZkw4Sw==
```
<h2>Decrypt</h2>

```python
from cryptonic import *
#Pattern creating
myPatternLen = 1024 # 1024 bytes
patternKey = createCryptonicKey(myPatternLen)
#Class building
myCrypter = cryptonic(pattern=patternKey) #Or myCrypter = cryptonic(cryptonicLen=1024) Or myCrypter = cryptonic(patternFilename="test.cton")
#Encrypting
encryptedMessage = myCrypter.encode(data="Hello world!") # Returns Tuple (isSuccess,EncryptedText)
if(encryptedMessage[0]):
    print "Encrypted message : %s"%(encryptedMessage[1])
else:
    print "Encrypt failed."
#Decrypting
if(encryptedMessage[0]):
    decryptedMessage = myCrypter.decode(encryptedMessage[1]) # Return Tuple (isSucess,DecryptedText)
    if(decryptedMessage[0]):
        print "Decrypt success."
        print "Message : %s"%(decryptedMessage[1])
    else:
        print "Failed."
        print "Pattern key not invalid"
else:
    pass
```
<h3>Output</h3>

```
Encrypted message : bTFTVXoxNVdDcGhWejE4WQ==
Decrypt success.
Message : Hello world!
```

<h1>Classes,Variables and Functions</h1>
<h2>cryptonic Class init</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer)
```

<h2>cryptonic Class encode</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer).encode(data=String)
```

<h2>cryptonic Class decode</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer).decode(data=String)
```

<h2>cryptonic Class encodeFile</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer).encodeFile(fname=String)
```

<h2>cryptonic Class decodeFile</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer).decodeFile(fname=String,nt=Boolean) # nt => file (decode) tag
```

<h2>cryptonic Class patternSave</h2>

```python
cryptonic(pattern=String,patternFilename=String,cryptonicLen=Integer).patternSave(fname=String)
```

<h2>fusion Class init</h2>

```python
fusion(filename=String)
```

<h3>Need this function</h3>

```python
import os
def getFolderTree(path):
    fileTree = dict()
    for root, dirs, files in os.walk(path):
        fileTree[root] = files
    return fileTree
```

<h2>fusion Class triggerFusion</h2>

```python
fusion(filename=String).triggerFusion(fileTree=Dict)
```

<h2>fusion Class encode</h2>

```python
fusion(filename=String).encode(data=String)
```

<h2>fusion Class decode</h2>

```python
fusion(filename=String).decode(data=String)
```

<h2>fusion Class triggerFission</h2>

```python
fusion(filename=String).triggerFission()
```

<h2>createCryptonicKey function</h2>

```python
createCryptonicKey(codecLen = 4) # codecLen => pattern size
```

<h2>getFileData function</h2>

```python
getFileData(fname=String)
```

<h2>patternRead function</h2>

```python
patternRead(fname=String)
```

<h1> CRYPTONIC WRITTEN BY SEPTILLIONER </h1>
<h2> THANKS FOR SUPPORTS HeykLog && Рнаитом </h2>
<h3> TR-EN </h3>
<h4> Licensed By MIT </h4>


