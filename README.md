# PZ Optimization 589f2f3f — 비공개 빌드

**Project Zomboid Build 42.21 / 게임 리비전 `4a0e9546ec` 전용**

PZ Optimization 제작자 **xD3I**가 2026년 10월 26일 Discord `#pre-release-testing` 채널에 공개한 비공개 개발 빌드입니다.

제작자의 재배포 허락을 받아 한국 커뮤니티에 공유합니다. 정식 안정판이 아니므로 설치 전 주의사항을 확인하세요.

| 항목 | 내용 |
| --- | --- |
| 제작자 | xD3I |
| 빌드 | `589f2f3f` |
| 배포일 | 2026년 10월 26일 |
| 지원 게임 | Project Zomboid Build 42.21 |
| 게임 리비전 | `4a0e9546ec` |
| 지원 운영체제 | Windows / Linux / macOS |
| 배포 유형 | 비공개 개발 빌드 |

**관련 저장소**

- [PZ Optimization 원본](https://github.com/xD3I/PZ_Optimization)
- [한국어 배포 저장소](https://github.com/bongmyung-ye/PZ-Optimization-KR)
- [한국어 패치 소스](https://github.com/bongmyung-ye/pzopt-korean)

---

## 주요 변경 사항

### 성능 및 모드 호환성

- 모드 Lua 이벤트 처리 개선
- 좀비 업데이트 및 맵 청크 처리 조정
- 모드가 많은 환경에서 저장 파일 불러오기 속도 개선
- 이벤트 처리 및 Lua와 Java 간 호출 성능 개선
- 반복적으로 발생하는 모드 오류의 로그 출력 제한

### 설정 화면 및 벤치마크

- PZ Optimization 설정 화면 개편
- 설정별 성능 영향 및 권장 사항 표시
- 전체 최적화 및 그래픽 향상 프리셋 추가
- 게임 내 벤치마크 화면 개선
- Horde Shooting 벤치마크 추가

### 입력 및 그래픽

- 컨트롤러 입력 지연 개선
- 화면 키보드 반응 속도 개선
- 나무와 지형에서 발생하는 화면 깜빡임 수정
- 여러 칸을 차지하는 가구의 연결 부위 표시 개선

### 신규 기능 (기본값 비활성화)

- Lua 컴파일러 및 테이블 메모리 최적화
- 개선된 손전등 그림자
- 가로등, 실내 조명, 화염 등의 추가 그림자
- 수면 반사 효과
- 지형 타일 경계 개선
- 계절별 지면 장식과 낙엽 효과
- 서리, 눈, 젖은 아스팔트의 반짝임 효과
- 바퀴 자국 및 잔디 눌림 효과
- 잔디 표현 개선

자세한 내용은 [변경 내역](https://github.com/bongmyung-ye/PZ-Optimization-KR/blob/main/CHANGES.md)을 참고하세요.

---

## 다운로드

[**GitHub Releases에서 다운로드**](https://github.com/bongmyung-ye/PZ-Optimization-KR/releases/tag/589f2f3f-test)

| 파일 | 설명 |
| --- | --- |
| `pzopt-589f2f3f.zip` | PZ Optimization 원본 비공개 빌드 |
| `PZOptKorean-589f2f3f.zip` | 해당 빌드용 한국어 패치 |

> GitHub에서 자동으로 제공하는 `Source code (zip)` 파일은 설치용 파일이 아닙니다. 반드시 **Assets**에 첨부된 ZIP 파일을 다운로드하세요.

---

## 설치 방법

### 1. PZ Optimization 설치 (Windows)

설치 전에 게임을 완전히 종료하고, 저장 파일과 기존 게임 설정을 백업하세요.

1. `pzopt-589f2f3f.zip`을 다운로드합니다.
2. 압축을 해제합니다.
3. `install.ps1`과 `pzopt-4a0e9546ec-classes.zip`이 들어 있는 폴더를 엽니다.
4. 탐색기 주소창에 `powershell`을 입력해 해당 폴더에서 PowerShell을 실행합니다.
5. 아래 명령어를 입력합니다.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Zip .\pzopt-4a0e9546ec-classes.zip
```

**설치 상태 확인**

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Status
```

**제거**

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Uninstall
```

### 2. 한국어 패치 설치 (Windows)

원본 최적화 모드를 설치한 다음 한국어 패치를 적용하세요.

1. `PZOptKorean-589f2f3f.zip`을 다운로드합니다.
2. 압축을 해제합니다.
3. 압축파일 안의 `PZOptKorean` 폴더를 `%USERPROFILE%\Zomboid\mods`에 복사합니다.
4. 게임을 실행하고 모드 목록에서 `PZOptKorean`을 활성화합니다.
5. PZ Optimization 설정 화면에서 한국어가 정상적으로 표시되는지 확인합니다.

설치 후 폴더 구조는 다음과 같아야 합니다.

```text
Zomboid/
└── mods/
    └── PZOptKorean/
        └── 42.0/
            ├── mod.info
            ├── icon.png
            └── media/
                └── lua/
                    ├── client/
                    └── shared/
```

| 항목 | 내용 |
| --- | --- |
| 패치 이름 | PZ Optimization 한국어 패치 |
| Mod ID | `PZOptKorean` |
| 대상 빌드 | `589f2f3f` |
| 설치 방식 | 로컬 모드 |
| 설치 경로 | `%USERPROFILE%\Zomboid\mods\PZOptKorean` |

**기존 창작마당 한국어 패치나 이전 테스트용 패치는 동시에 활성화하지 마세요.**

한국어 패치만 제거하려면 게임을 종료하고 설치한 로컬 `PZOptKorean` 폴더를 제거하면 됩니다.

### 3. Linux / macOS

원본 ZIP을 압축 해제한 뒤 `install.sh`가 있는 디렉터리에서 다음 명령어를 실행합니다.

```bash
bash install.sh --zip pzopt-4a0e9546ec-classes.zip
```

Linux와 macOS의 원본 설치 방법은 [설치 안내](https://github.com/bongmyung-ye/PZ-Optimization-KR/blob/main/INSTALL.md)를 참고하세요. 한국어 패치의 설치 위치는 운영체제별 사용자 모드 경로를 확인해야 합니다.

---

## 파일 무결성 확인 (SHA-256)

| 파일 | SHA-256 |
| --- | --- |
| `pzopt-589f2f3f.zip` | `c4ea4f9d8df03352f2f7e6a0ef24ca5bbda66ae6c42c77b7d2a5d3384ca66009` |
| `pzopt-4a0e9546ec-classes.zip` | `bd1ff13d83a2e8739ade95ec8ca8e32212b70c1f04a310803cc1432dc69a4e30` |
| `PZOptKorean-589f2f3f.zip` | `abe6801f927ee0d08d1382af28ba3f340be8eb5e5ca285351e8626fc816b7328` |

Windows에서는 다운로드한 ZIP 파일이 있는 폴더에서 다음 명령어로 확인할 수 있습니다.

```powershell
Get-FileHash -Algorithm SHA256 ".\pzopt-589f2f3f.zip"
Get-FileHash -Algorithm SHA256 ".\PZOptKorean-589f2f3f.zip"
```

---

## 주의사항

- 이 빌드는 **Project Zomboid Build 42.21 / 게임 리비전 `4a0e9546ec` 전용**입니다.
- 게임 리비전이 다르면 설치하지 마세요.
- 정식 안정판이 아닌 비공개 개발 빌드입니다. 게임 설정과 저장 파일을 백업한 뒤 설치하세요.
- 다른 Java 모드가 동일한 클래스 파일을 수정하는 경우 설치가 중단될 수 있습니다.
- 충돌 원인을 확인하지 않은 상태에서 `-Force` 옵션을 사용하지 마세요.
- 원본 모드와 한국어 패치는 별도의 ZIP으로 배포합니다.
- 기존 창작마당 한국어 패치와 이번 한국어 패치를 중복으로 활성화하지 마세요.
- 원본 모드가 업데이트되면 현재 한국어 패치와 호환되지 않을 수 있습니다.
- 한국어 패치를 제거하더라도 PZ Optimization 원본은 자동으로 제거되지 않습니다.

---

## 제작자 및 배포 안내

**PZ Optimization**

- 제작자: [xD3I](https://github.com/xD3I)
- 원본 저장소: https://github.com/xD3I/PZ_Optimization

**한국어 패치 및 커뮤니티 배포**

- 관리: [bongmyung-ye](https://github.com/bongmyung-ye)
- 한국어 패치 소스: https://github.com/bongmyung-ye/pzopt-korean
- 배포 저장소: https://github.com/bongmyung-ye/PZ-Optimization-KR

PZ Optimization 원본의 저작권은 제작자에게 있습니다.

이 저장소는 제작자의 재배포 허락을 받아 비공개 개발 빌드를 공유하고, 한국어 설치 안내와 별도 한국어 패치를 제공하기 위해 운영합니다.

본 저장소는 PZ Optimization의 공식 개발 저장소가 아닙니다.
