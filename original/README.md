This directory contains the original APK files, used as a base for generating patches for each version. The authenticity of the app can be verified by checking the signature:

```
> apksigner verify --print-certs <file>.apk

Signer #1 certificate DN: CN=Jio, OU=RJIL, O=Reliance, L=Mumbai, ST=Maharashtra, C=IN
Signer #1 certificate SHA-256 digest: 564c04d1382c959329c6f47e95d497afd151210e4d9426814feb6fa57af7ad30
Signer #1 certificate SHA-1 digest: 247775a14796b7b07db871ea382c983da4116c13
Signer #1 certificate MD5 digest: 5fb35dc755664f338b4ec6af7e7f8cdb
Source Stamp Signer certificate DN: CN=Android, OU=Android, O=Google Inc., L=Mountain View, ST=California, C=US
Source Stamp Signer certificate SHA-256 digest: 3257d599a49d2c961a471ca9843f59d341a405884583fc087df4237b733bbd6d
Source Stamp Signer certificate SHA-1 digest: b1af3a0bf998aeede1a8716a539e5a59da1d86d6
Source Stamp Signer certificate MD5 digest: 577b8a9fbc7e308321aec6411169d2fb
```
