# SIVI Resource Packs

Resource pack cho server Minecraft **SIVI** (Paper 26.1.2, `pack_format` 84).

Repo nay chi de **host file** cho server tu day ve client. Khong chua ma nguon.

## Danh sach pack

| File | Namespace | Kich thuoc | SHA1 |
|---|---|---|---|
| `cclast-rsp-26.1.2.zip` | `fw`, `space`, `minecraft` | 16.582.888 B | `195efd01a031d4c9764e6e36b1654ee75c6b9152` |
| `zas-music-test.zip` | `zas`, `minecraft` | 7.950.043 B | `cc034caaa22624a9112b2006a31f57f321ac7e51` |
| `endfield-fmg-26.1.2.zip` | `fmg` | 33.420 B | `24604a75ad19dfd261465e218c7563b8a65f9e82` |
| `sivi-props-rsp.zip` | `sivi`, `minecraft` | 26.084 B | `e4947a159ded6f2b444206adf0a5b7c5e68e9d96` |

Da do bang cong cu doi chieu: **2006 duong dan duy nhat, 0 file de nhau**
(chi `pack.mcmeta` trung ten, moi pack giu ban rieng khi tai chong len nhau).

## Cach dung

Server day ca 4 pack cung luc qua API `ResourcePackRequest` (Minecraft 1.20.3+
cho phep xep chong nhieu pack). Client tai lan luot theo thu tu liet ke.

URL on dinh (dung **tag**, khong dung `main`, de client cache duoc):

```
https://raw.githubusercontent.com/ObsidianMC123/sivi-resourcepacks/v1/<ten-file>.zip
```

Moi lan cap nhat pack phai tao **tag moi** (`v2`, `v3`...) — giu nguyen URL cu
thi client van dung ban da cache.

## Luu y

- File `.gitattributes` dat `*.zip binary` de git khong doi CRLF lam hong zip.
- SHA1 o bang tren phai khop voi hash server gui cho client, khong thi client
  se tai lai moi lan vao game thay vi dung cache.
