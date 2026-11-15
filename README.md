# 2026-1-VR-AR

2026년 3학년 1학기 **가상현실과 증강현실** 수업 Unity 프로젝트 원본 백업.

원본 zip은 용량 때문에 git이 아니라 **[Releases → backup-2026-11-15](../../releases/tag/backup-2026-11-15)** 에 첨부되어 있다.
GitHub Release 첨부 파일은 개당 2GB 제한이 있어서 큰 zip은 1.9GB 단위로 나눠 올렸다.

| 프로젝트 | Release 첨부 파일 | 원본 크기 (byte) |
|---|---|---|
| Escape Room | `Escape.Room.zip` (분할 없음, 내려받은 뒤 `Escape Room.zip`으로 이름 바꿔도 됨) | 1,418,775,850 |
| MyArProject | `MyArProject.zip.001` ~ `.003` | 5,910,664,362 |
| Tower_Defence_forAR | `Tower_Defence_forAR.zip.001` ~ `.003` | 5,485,079,965 |

## 복원 방법

조각 파일을 한 폴더에 모두 내려받은 뒤, 아래 중 하나로 합친다.

**cmd**
```bat
copy /b MyArProject.zip.001+MyArProject.zip.002+MyArProject.zip.003 MyArProject.zip
copy /b Tower_Defence_forAR.zip.001+Tower_Defence_forAR.zip.002+Tower_Defence_forAR.zip.003 Tower_Defence_forAR.zip
```

**Git Bash**
```bash
cat MyArProject.zip.0* > MyArProject.zip
cat Tower_Defence_forAR.zip.0* > Tower_Defence_forAR.zip
```

**7-Zip**: `.001` 파일 우클릭 → 7-Zip → 파일 합치기(Combine files)

## 무결성 확인

합친 zip의 SHA-256이 [`ORIGINAL_SHA256SUMS.txt`](ORIGINAL_SHA256SUMS.txt)와 같으면 원본과 동일하다.
조각별 해시는 [`PART_SHA256SUMS.txt`](PART_SHA256SUMS.txt)에 있다.

```powershell
Get-FileHash MyArProject.zip -Algorithm SHA256
```

```bash
sha256sum -c ORIGINAL_SHA256SUMS.txt
```
