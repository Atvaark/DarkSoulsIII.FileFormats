# DarkSoulsIII.FileFormats

## Tools

[BinderTool](https://github.com/Atvaark/BinderTool)

[DS3ParamExtractor](https://github.com/Pireax/DS3ParamExtractor)

[DirectXTex](https://github.com/Microsoft/DirectXTex)

Any text editor that supports Shift-JIS encoding

## Formats

Extension            | Description                                  | Tools
-------------------- | -------------------------------------------- | -------- 
.anibnd              | Animation archive                            | BinderTool
.bdt                 | General purpose archive                      | BinderTool
.behaviorstringid    |                                              |
.behbnd              | Character behaviour archive                  | BinderTool
.bhd                 | General purpose archive (header)             | BinderTool
.bnd                 | General purpose archive                      | BinderTool
.breakobj            | Destructible map objects                     |
.btab                |                                              |
.btl                 |                                              |
.btpb                |                                              |
.ccm                 |                                              |
.chrbnd              | Character archive                            | BinderTool
.chresdbnd           |                                              |
.chrtpfbhd           | Character texture archive                    | BinderTool
.dcx                 | Compressed file                              | BinderTool
.dds                 | DirectDraw Surface texture (DirectX 9/10/11) | DirectXTex
.drb                 |                                              |
.edf                 |                                              |
.eld                 |                                              |
.enc                 | Encrypted file                               | BinderTool
.entryfilelist       | Filename list                                |
.entryfilelistbnd    | Filename list archive                        |
.esd                 |                                              |
.evd                 |                                              |
.fev                 | Audio                                        |
.ffx                 |                                              |
.ffxbnd              | Audio archive                                | BinderTool
.flver               | 3D Model                                     | 
.fmg                 | Text                                         | BinderTool
.fpo                 |                                              |
.fsb                 | Audio                                        |
.gfx                 | 2D UI                                        |
.gparam              | Map graphics parameter                       |
.hkainvm             |                                              |
.hkainvmbnd          | Havok archive                                | BinderTool
.hkbbnd              |                                              |
.hkbscript           | Script                                       |
.hkx                 |                                              |
.hkxfilebnd          | Havok archive                                | BinderTool
.hkxpwv              |                                              |
.idname              |                                              |
.itl                 |                                              |
.loadlist            | Map description (plaintext)                  | Text editor
.loadlistlist        | Map description (plaintext)                  | Text editor
.lua                 | Script                                       |
.luabnd              | Script archive                               | BinderTool
.mapbnd              | Map archive                                  | BinderTool
.maptexture          |                                              |
.menuesdbnd          | Menu archive                                 | BinderTool
.mmb                 |                                              |
.movtae              |                                              |
.mqb                 |                                              |
.msb                 |                                              |
.msgbnd              | Text archive                                 | BinderTool
.msp                 |                                              |
.mtd                 | Material                                     |
.mtdbnd              | Material archive                             | BinderTool
.nfd                 |                                              |
.nva                 |                                              |
.objbnd              | Object archive                               | BinderTool
.onav                |                                              |
.param               | Game settings                                | BinderTool, DS3ParamExtractor
.parambnd            | Game settings archive                        | BinderTool
.paramdef            | Game settings definition                     |
.paramdefbnd         | Game settings definition archive             | BinderTool
.partsbnd            | Item archive                                 | BinderTool
.premapdecal         |                                              |
.regbnd              | Regulation archive                           | BinderTool
.remobnd             | Demo archive                                 | BinderTool
.rumblebnd           | Rumble settings archive                      | BinderTool
.shaderbdlebnd       | Shader archive                               | BinderTool
.shaderbdlebnddebug  | Shader archive                               | BinderTool
.shaderbnd           | Shader archive                               | BinderTool
.sl2                 | Savegame                                     | BinderTool
.stayparambnd        | Game settings archive                        | BinderTool
.stayparamdefbnd     | Game settings definition archive             | BinderTool
.talkeddbnd          | Talk archive                                 | BinderTool
.talkesdbnd          | Talk archive                                 | BinderTool
.texbnd              | Texture archive                              | BinderTool
.textlist            |                                              |
.tpf                 | Texture archive                              | BinderTool
.vpo                 |                                              |
.warppassage         |                                              |
.wcmsgbnd            | Word checker archive                         | BinderTool

## Encryption

### Regulation file (Data0.bdt)
Key         | Value
----------- | ----------------------------------------------------------------
Encryption  | AES CBC 256
Key         | "ds3#jn/8_7(rsY9pg55GFN7VFL#+3n/)" (ASCII)
IV          | First 16 bytes of the Data0.bdt file

### Archive header (Data1.bhd-Data5.bhd)
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
