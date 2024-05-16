## Verification of Electron cash official executables on Windows

### 1. Get all the files needed for verification

At the time this readme was updated, the latest version was 4.2.11  
The current latest version may be newer. Normally, you always should
be using the latest version.

Download the latest version from: [ElectronCash.org](https://electroncash.org/#download).

Next, [download the checksum and signature from GitHub](https://github.com/Electron-Cash/keys-n-hashes/tree/master/sigs-and-sums/4.2.11/win-linux) (for v4.2.11).

Files you need for Windows in this example are:

```
Electron-Cash-4.2.11.exe.asc
SHA256.Electron-Cash-4.2.11.exe.txt
```

### 2. Verify SHA256 digest hash

Download and install [7-zip](https://www.7-zip.org/download.html) software.

Right click on `ElectronCash-4.2.11.exe` and calculate sha256, which should be identical to that in `SHA256.ElectronCash-4.2.11.exe.txt` text file.

![](https://github.com/mpapec/docs/blob/master/sha256_1.png)

![](https://github.com/mpapec/docs/blob/master/sha256_2.png)

### 3. Verify author signature of executable file (optional step)

Download and install [gpg4win](https://www.gpg4win.org/) (gnupg for windows).

Download a public key from [GitHub](https://raw.githubusercontent.com/fyookball/keys-n-hashes/master/pubkeys/jonaldkey2.txt) and import it into gpg keychain:

```sh
gpg --import jonaldkey2.txt
```

which should give output like:

```sh
gpg: C:/Users/user/AppData/Roaming/gnupg/trustdb.gpg: trustdb created
gpg: key 4FD06489EFF1DDE1: public key "Jonald Fyookball <jonf@electroncash.org>" imported
```

and finally verify a signature:

```sh
gpg --verify ElectronCash-4.2.11.exe.sig
```

which should give a message with mandatory line `Good signature from "Jonald Fyookball <jonf@electroncash.org>"`

```sh
gpg: assuming signed data in 'ElectronCash-4.2.11.exe'
gpg: Signature made 03/17/18 21:30:44 W. Europe Standard Time
gpg:                using DSA key 4FD06489EFF1DDE1
gpg: Good signature from "Jonald Fyookball <jonf@electroncash.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: D56C 110F 4555 F371 AEEF  CB25 4FD0 6489 EFF1 DDE1
```

## Verification of Electron cash official executables on Linux

### 1. Get all the files needed for verification

At the time this readme was updated, the latest version was 4.2.11  
The current latest version may be newer. Normally, you always should
be using the latest version.

Download the latest version from: [ElectronCash.org](https://electroncash.org/#download).

Next, [download the checksum and signature from GitHub](https://github.com/Electron-Cash/keys-n-hashes/tree/master/sigs-and-sums/4.2.11/win-linux) (for v4.2.11).

Files you need for Linux in this example are:

```
Electron-Cash-4.2.11-x86_64.AppImage.asc
SHA256.Electron-Cash-4.2.11-x86_64.AppImage.txt
```

### 2. Verify SHA256 digest hash

On command line run a command:

```sh
cat SHA256.Electron-Cash-4.2.11-x86_64.AppImage.txt && openssl sha256 -r Electron-Cash-4.2.11-x86_64.AppImage
```

which should confirm that both SHA256 hashes are identical:

```sh
378117e584e000ab9b316fe6efd74992021f2a332e6986d2324cee6eee3f5486  Electron-Cash-4.2.11-x86_64.AppImage
378117e584e000ab9b316fe6efd74992021f2a332e6986d2324cee6eee3f5486 *Electron-Cash-4.2.11-x86_64.AppImage
```

### 3. Verify author signature of executable file (optional step)

Install gnupg package,

```sh
sudo apt-get install gnupg2
```

Download a public key and import it into gpg keychain,

```sh
gpg2 --import <(curl -L https://raw.githubusercontent.com/fyookball/keys-n-hashes/master/pubkeys/jonaldkey2.txt)
```

which should give output like:

```sh
gpg: key EFF1DDE1: public key "Jonald Fyookball <jonf@electroncash.org>" imported
gpg: Total number processed: 1
gpg:               imported: 1
```

and finally verify a signature:

```sh
gpg2 --verify Electron-Cash-4.2.11-x86_64.AppImage.asc
```

which should give a message with mandatory line `Good signature from "Jonald Fyookball <jonf@electroncash.org>"`

```sh
gpg: assuming signed data in 'Electron-Cash-4.2.11-x86_64.AppImage'
gpg: Signature made Sat 17 Mar 2018 09:31:10 PM STD using DSA key ID EFF1DDE1
gpg: Good signature from "Jonald Fyookball <jonf@electroncash.org>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: D56C 110F 4555 F371 AEEF  CB25 4FD0 6489 EFF1 DDE1
```

## Verification of Electron cash official executables on OS X

### 1. Get all the files needed for verification

At the time this readme was updated, the latest version was 4.2.11  
The current latest version may be newer. Normally, you always should
be using the latest version.

Download the latest version from: [ElectronCash.org](https://electroncash.org/#download).

Next, [download the checksum and signature from GitHub](https://github.com/Electron-Cash/keys-n-hashes/tree/master/sigs-and-sums/4.2.11/mac) (for v4.2.11).

Files you need for Mac OS X in this example are:

```
Electron-Cash-4.2.11-macosx.dmg.asc
Electron-Cash-4.2.11-macosx.dmg.sha256sum
```

### 2. Verify SHA256 digest hash

On command line run a command,

```sh
cat Electron-Cash-4.2.11-macosx.dmg.sha256sum && openssl sha256 -r Electron-Cash-4.2.11-macosx.dmg
```

which should confirm that both SHA256 hashes are identical:

```sh
e10ee7b1bff75207087c489d1ad868dbc39be292ef6b53daa9b1f1c62d7db4fc Electron-Cash-4.2.11-macosx.dmg
e10ee7b1bff75207087c489d1ad868dbc39be292ef6b53daa9b1f1c62d7db4fc *Electron-Cash-4.2.11-macosx.dmg
```

### 3. Verify author signature of executable file (optional step)

Download and install [gpgtools](https://gpgtools.org/) (gnupg for osx).

Download a public key and import it into gpg keychain:

```sh
gpg2 --import <(curl -L 'http://ipv4.pool.sks-keyservers.net/pks/lookup?op=get&search=0x21810A542031C02C')
```

Which should give output like:

```sh
gpg: key 2031C02C: public key "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>" imported
gpg: Total number processed: 1
gpg:               imported: 1
gpg: no ultimately trusted keys found
```

and finally verify a signature:

```sh
gpg2 --verify Electron-Cash-4.2.11-macosx.dmg.asc
```

which should give a message with mandatory line `Good signature from "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>"`

```sh
gpg: assuming signed data in 'Electron-Cash-4.2.11-macosx.dmg'
gpg: Signature made Sat 17 Mar 2018 10:41:55 PM STD using DSA key ID 2031C02C
gpg: Good signature from "Calin Culianu (NilacTheGrim) <calin.culianu@gmail.com>" [unknown]
gpg: WARNING: This key is not certified with a trusted signature!
gpg:          There is no indication that the signature belongs to the owner.
Primary key fingerprint: D465 135F 97D0 047E 18E9  9DC3 2181 0A54 2031 C02C
```
