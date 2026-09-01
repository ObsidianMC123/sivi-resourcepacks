# SIVI Resource Packs

Resource pack cho server Minecraft **SIVI** (Paper 26.1.2, `pack_format` 84).

Repo nay chi de **host file** cho server tu day ve client. Khong chua ma nguon.

## Danh sach pack

| File | Tag | Namespace | Kich thuoc | SHA1 |
|---|---|---|---|---|
| `cclast-rsp-26.1.2.zip` | `v1` | `fw`, `space`, `minecraft` | 16.582.888 B | `195efd01a031d4c9764e6e36b1654ee75c6b9152` |
| `zas-music-test.zip` | `v1` | `zas`, `minecraft` | 7.950.043 B | `cc034caaa22624a9112b2006a31f57f321ac7e51` |
| `endfield-fmg-26.1.2.zip` | `v1` | `fmg` | 33.420 B | `24604a75ad19dfd261465e218c7563b8a65f9e82` |
| `betterhud-26.1.2.zip` | `v2` | `betterhud`, `minecraft` | 4.552.312 B | `cce5c0ff9bcd24bee179bdf718895df2783eeacf` |
| `sivi-props-rsp.zip` | `v1` | `sivi`, `minecraft` | 24.961 B | `04b2c7373c4bad79a740aa2a53859057566e0be7` |

Da do lai bang cong cu doi chieu (01/09/2026): **3161 duong dan duy nhat, 0 file de nhau**.
Chi `pack.mcmeta` va `pack.png` trung ten giua cac pack, nhung moi pack giu ban
rieng cua no nen khong anh huong gi.

## Cach dung

Server day ca 5 pack cung luc qua API `ResourcePackRequest` (Minecraft 1.20.3+
cho phep xep chong nhieu pack). Client tai lan luot theo thu tu liet ke, pack
nam sau de len pack nam truoc neu trung duong dan file.

URL on dinh (dung **tag**, khong dung `main`, de client cache duoc):

```
https://raw.githubusercontent.com/ObsidianMC123/sivi-resourcepacks/<tag>/<ten-file>.zip
```

Moi lan them hoac cap nhat pack phai tao **tag moi** (`v2`, `v3`...) — cac pack
cu van giu URL tag cu nen client khong phai tai lai.

## Ghi chu ve `betterhud-26.1.2.zip`

Pack nay do plugin **BetterHud 2.0.0** tu sinh ra o `plugins/BetterHud/build/`,
khong sua tay. Trong `pack.mcmeta` co co che `overlays` anh xa `pack_format`
sang thu muc shader tuong ung, nen mot file zip chay duoc nhieu doi client:

| Dai format | Thu muc overlay |
|---|---|
| 9 - 45 | `betterhud_1_21_2` |
| 46 - 55 | `betterhud_1_21_4` |
| 56 - 83 | `betterhud_1_21_6` |
| 84 - 99 | `betterhud_26_1` |

Khi dong goi lai phai giu **du ca 4 thu muc overlay** va de `pack.mcmeta` o
**goc zip** (khong boc them mot lop thu muc).

Vi `plugins/BetterHud/config.yml` dat `clear-build-folder: true`, thu muc
`build/` bi xoa va dung lai moi lan server khoi dong. Neu doi asset hoac doi
ban BetterHud thi zip phai dong goi lai, SHA1 doi theo, va phai cap nhat ca
`SiviPack/config.yml` lan bang tren. Script dong goi (co dat timestamp co dinh
de zip deterministic) nam o `_staging-betterhud/mkzip.ps1`.

## Luu y

- File `.gitattributes` dat `*.zip binary` de git khong doi CRLF lam hong zip.
- SHA1 o bang tren phai khop voi hash server gui cho client, khong thi client
  se tai lai moi lan vao game thay vi dung cache.
- `SiviPack` dat `required: true` va `kick-on` co `FAILED_DOWNLOAD` — sai hash
  hoac chet URL la nguoi choi bi kick. Buoc `preflight` se chan truoc bang HEAD
  request nen URL chet thi pack do khong duoc day, khong kick vi no.
