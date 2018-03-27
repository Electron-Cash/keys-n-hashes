## Verification of Electron cash official executables on Windows

### 1. Get all the files needed for verification

    https://electroncash.org/downloads/3.1.6/win-linux/ElectronCash-3.1.6.exe
from [electroncash.org](https://electroncash.org/downloads/3.1.6/win-linux/ElectronCash-3.1.6.exe), and 

    SHA256sum.ElectronCash-3.1.6.exe.txt
    ElectronCash-3.1.6.exe.sig
from [GitHub](https://github.com/fyookball/keys-n-hashes/tree/master/sigs-and-sums/3.1.6/win-linux)

###  2. Verify sha256 digest hash
Download and install [7-zip](https://www.7-zip.org/download.html) software.

Right click on `ElectronCash-3.1.6.exe` and calculate sha256, which should be identical to that in `SHA256sum.ElectronCash-3.1.6.exe.txt` text file.

![](https://github.com/mpapec/docs/blob/master/sha256_1.png)

![](https://github.com/mpapec/docs/blob/master/sha256_2.png)


### 3. Verify author signature of executable file (optional step)

Download and install [gpg4win](https://www.gpg4win.org/) (gnupg for windows).

Download a public key from [GitHub](https://raw.githubusercontent.com/fyookball/keys-n-hashes/master/pubkeys/jonaldkey2.txt) and import it into gpg keychain,

    gpg --import jonaldkey2.txt
which should give output like,

    gpg: C:/Users/user/AppData/Roaming/gnupg/trustdb.gpg: trustdb created
    gpg: key 4FD06489EFF1DDE1: public key "Jonald Fyookball <jonf@electroncash.org>" imported

and finally verify a signature,

    gpg --verify ElectronCash-3.1.6.exe.sig
which should give a message with mandatory line `Good signature from "Jonald Fyookball <jonf@electroncash.org>"`

    gpg: assuming signed data in 'ElectronCash-3.1.6.exe'
    gpg: Signature made 03/17/18 21:30:44 W. Europe Standard Time
    gpg:                using DSA key 4FD06489EFF1DDE1
    gpg: Good signature from "Jonald Fyookball <jonf@electroncash.org>" [unknown]
    gpg: WARNING: This key is not certified with a trusted signature!
    gpg:          There is no indication that the signature belongs to the owner.
    Primary key fingerprint: D56C 110F 4555 F371 AEEF  CB25 4FD0 6489 EFF1 DDE1

## Verification of Electron cash official executables on Linux


### 1. Get all the files needed for verification

    https://electroncash.org/downloads/3.1.6/win-linux/ElectronCash-3.1.6.tar.gz
from [electroncash.org](https://electroncash.org/downloads/3.1.6/win-linux/ElectronCash-3.1.6.tar.gz), and 

    SHA256sum.ElectronCash-3.1.6.tar.gz.txt
    ElectronCash-3.1.6.tar.gz.sig
from [GitHub](https://github.com/fyookball/keys-n-hashes/tree/master/sigs-and-sums/3.1.6/win-linux)

###  2. Verify sha256 digest hash
On command line run a command,

    cat SHA256sum.ElectronCash-3.1.6.tar.gz.txt && openssl sha256 -r ElectronCash-3.1.6.tar.gz
which should confirm that both SHA256 hashes are identical,

    b5a1d28ef13e80ce221aa6d677f4ef8585f29c8f6f3b97fb07e13209782c5318  ElectronCash-3.1.6.tar.gz
    b5a1d28ef13e80ce221aa6d677f4ef8585f29c8f6f3b97fb07e13209782c5318 *ElectronCash-3.1.6.tar.gz

### 3. Verify author signature of executable file (optional step)

Install gnupg package,

    sudo apt-get install gnupg2

Download a public key and import it into gpg keychain,

    gpg2 --import <(curl -L https://raw.githubusercontent.com/fyookball/keys-n-hashes/master/pubkeys/jonaldkey2.txt)

which should give output like,

    gpg: key EFF1DDE1: public key "Jonald Fyookball <jonf@electroncash.org>" imported
    gpg: Total number processed: 1
    gpg:               imported: 1

and finally verify a signature,

    gpg2 --verify ElectronCash-3.1.6.tar.gz.sig
which should give a message with mandatory line `Good signature from "Jonald Fyookball <jonf@electroncash.org>"`

    gpg: assuming signed data in 'ElectronCash-3.1.6.tar.gz'
    gpg: Signature made Sat 17 Mar 2018 09:31:10 PM STD using DSA key ID EFF1DDE1
    gpg: Good signature from "Jonald Fyookball <jonf@electroncash.org>" [unknown]
    gpg: WARNING: This key is not certified with a trusted signature!
    gpg:          There is no indication that the signature belongs to the owner.
    Primary key fingerprint: D56C 110F 4555 F371 AEEF  CB25 4FD0 6489 EFF1 DDE1
    
## Verification of Electron cash official executables on OS X


### 1. Get all the files needed for verification

    https://electroncash.org/downloads/3.1.6/mac/Electron-Cash-3.1.6-macosx.dmg
from [electroncash.org](https://electroncash.org/downloads/3.1.6/mac/Electron-Cash-3.1.6-macosx.dmg), and 

    Electron-Cash-3.1.6-macosx.dmg.sha256sum
    Electron-Cash-3.1.6-macosx.dmg.sig
from [GitHub](https://github.com/fyookball/keys-n-hashes/tree/master/sigs-and-sums/3.1.6/mac)

###  2. Verify sha256 digest hash
On command line run a command,

    cat Electron-Cash-3.1.6-macosx.dmg.sha256sum && openssl sha256 -r Electron-Cash-3.1.6-macosx.dmg
which should confirm that both SHA256 hashes are identical,

    8a6a6a813c2ea6f714d1e29b16f8775e150cd0ef1149f5f472683d684c1558fa *Electron-Cash-3.1.6-macosx.dmg
    8a6a6a813c2ea6f714d1e29b16f8775e150cd0ef1149f5f472683d684c1558fa *Electron-Cash-3.1.6-macosx.dmg

### 3. Verify author signature of executable file (optional step)

Download and install [gpgtools](https://gpgtools.org/) (gnupg for osx).

Download a public key and import it into gpg keychain,

    gpg2 --import <(curl -L 'http://ipv4.pool.sks-keyservers.net/pks/lookup?op=get&search=0x21810A542031C02C')
which should give output like,

    gpg: key 2031C02C: public key "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>" imported
    gpg: Total number processed: 1
    gpg:               imported: 1
    gpg: no ultimately trusted keys found

and finally verify a signature,

    gpg2 --verify Electron-Cash-3.1.6-macosx.dmg.sig
which should give a message with mandatory line `Good signature from "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>"`

    gpg: assuming signed data in 'Electron-Cash-3.1.6-macosx.dmg'
    gpg: Signature made Sat 17 Mar 2018 10:41:55 PM STD using DSA key ID 2031C02C
    gpg: Good signature from "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>" [unknown]
    gpg: WARNING: This key is not certified with a trusted signature!
    gpg:          There is no indication that the signature belongs to the owner.
    Primary key fingerprint: D465 135F 97D0 047E 18E9  9DC3 2181 0A54 2031 C02C
