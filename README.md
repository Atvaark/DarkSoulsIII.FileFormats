# DarkSoulsIII.FileFormats

## Encryption

### Regulation (data0)
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | RSA 2048
Key         | Unknown
Remarks     | The game uses OpenSSL and Eric Young's PKCS#1 RSA_eay_public_decrypt function (obfuscated rsa_lib.c)

### Archives (data1-data5)

Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | RSA 2048
Key         | See [keys.pem](keys.pem)
Remarks     | The game uses OpenSSL and Eric Young's PKCS#1 RSA_eay_public_decrypt function (obfuscated rsa_lib.c)

### Savegames
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES unknown length/mode
Key         | Unknown
IV          | Unknown
