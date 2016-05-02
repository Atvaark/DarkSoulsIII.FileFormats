# DarkSoulsIII.FileFormats

## Encryption

### Regulation file (data0.bdt)
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES CBC 256
Key         | "ds3#jn/8_7(rsY9pg55GFN7VFL#+3n/)" (ASCII)
IV          | First 16 bytes of the data0.bdt file

### Archive header (data1.bhd-data5.bhd)
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | RSA 2048
Key         | See [keys.pem](keys.pem)

### Archive data (data1.bdt-data5.bdt)
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES ECB 128
Key         | Stored in the corresponding .bhd file. (Unique for each encrypted file.)

### Savegames
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES CBC 128
Key         | FD464D695E69A39A10E319A7ACE8B7FA
IV          | First 16 bytes of the USER_DATA files inside .sl2 file

### Network Session
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES CBC 128
Key         | "ds3vvhes09djxwcj" (ASCII)
IV          | Unknown
