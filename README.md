# AES
C++ AES(Advanced Encryption Standard) implementation  
 
![Build Status](https://travis-ci.org/SergeyBel/AES.svg?branch=master)


**This class is very simple to use:**
```c++
...


unsigned char plain[] = { 0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff }; //plaintext example
unsigned char key[] = { 0x00, 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x0a, 0x0b, 0x0c, 0x0d, 0x0e, 0x0f }; //key example
unsigned int plainLen = 16 * sizeof(unsigned char);  //bytes in plaintext
unsigned int outLen = 0;  // out param - bytes in сiphertext

AES aes(128);  //128 - key length, can be 128, 192 or 256
c = aes.EncryptECB(plain, plainLen, key, outLen);
//now variable c contains outLen bytes - ciphertext
...
```
Or for vectors:
```c++
...


vector<unsigned char> plain = { 0x00, 0x11, 0x22, 0x33, 0x44, 0x55, 0x66, 0x77, 0x88, 0x99, 0xaa, 0xbb, 0xcc, 0xdd, 0xee, 0xff }; //plaintext example
vector<unsigned char> key = { 0x00, 0x01, 0x02, 0x03, 0x04, 0x05, 0x06, 0x07, 0x08, 0x09, 0x0a, 0x0b, 0x0c, 0x0d, 0x0e, 0x0f }; //key example

AES aes(128);
c = aes.EncryptECB(plain, key);
//now vector c contains ciphertext
...
```
ECB, CBC, CFB modes are supported.


You can read more about AES here:

https://en.wikipedia.org/wiki/Advanced_Encryption_Standard

http://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.197.pdf


**Development:**
1. `git clone https://github.com/SergeyBel/AES.git`
1. `docker-compose build`
1. `docker-compose up -d`
1. use make commands

There are four executables in `bin` folder:  
* `test` - run tests  
* `debug` - version for debugging (main code will be taken from dev/main.cpp)  
* `profile` - version for profiling with gprof (main code will be taken from dev/main.cpp)  
* `release` - version with optimization (main code will be taken from dev/main.cpp)  


Build commands:  
* `make build_all` - build all targets
* `make build_test` - build `test` target
* `make build_debug` - build `debug` target
* `make build_profile` - build `profile` target
* `make build_release` - build `release` target
* `make test` - run tests
* `make debug` - run debug version
* `make profile` - run profile version
* `make release` - run `release` version
* `make clean` - clean `bin` directory
