# 설치 및 제거 안내

대상: **Project Zomboid Build 42.21 / 게임 리비전 `4a0e9546ec`**  
배포 빌드: **PZ Optimization `589f2f3f`**

설치 스크립트는 게임 폴더 안에 파일을 추가하고 실행 설정을 확인합니다. 기존 PZ Optimization 설치가 있다면 교체될 수 있으므로, 먼저 게임을 종료하고 필요한 파일을 백업하세요.

## 1. 설치 준비

1. 게임을 완전히 종료합니다. 별도로 실행 중인 서버가 있다면 종료 여부를 먼저 확인하세요.
2. `%USERPROFILE%\Zomboid\Saves` 또는 사용 중인 저장 파일을 백업합니다. 멀티플레이 서버는 서버의 저장 파일을 별도로 백업하세요.
3. 게임 폴더의 `ProjectZomboid64.json`을 수정한 적이 있다면 사본을 보관합니다.
4. GitHub Releases에서 **`pzopt-589f2f3f.zip`**을 받아 압축을 풉니다.
5. 압축을 푼 `pzopt-589f2f3f-discord` 폴더에 아래 파일이 있는지 확인합니다.

```text
pzopt-589f2f3f-discord/
├─ README.txt
├─ install.ps1
├─ install.sh
├─ uninstall.ps1
├─ uninstall.sh
└─ pzopt-4a0e9546ec-classes.zip
```

**주의:** `uninstall.ps1`과 `uninstall.sh`는 최신 공개 설치 프로그램을 인터넷에서 받아 실행합니다. 이 테스트 빌드를 제거할 때는 해당 파일 대신 아래에 안내한 **`install.ps1 -Uninstall`** 또는 **`install.sh --uninstall`**을 사용하세요.

## 2. Windows

### 설치

1. 압축을 푼 `pzopt-589f2f3f-discord` 폴더를 엽니다.
2. 탐색기 주소창에 `powershell`을 입력하고 Enter를 누릅니다.
3. 다음 명령을 실행합니다.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Zip .\pzopt-4a0e9546ec-classes.zip
```

설치 프로그램이 Steam 라이브러리에서 게임 폴더를 찾고, 게임 리비전과 설치 파일의 리비전을 확인합니다. 설치가 끝나면 `installed ... files` 메시지가 표시됩니다.

게임 폴더 자동 검색에 실패하면 `-Dir` 옵션으로 경로를 직접 지정합니다. 아래 경로는 예시이므로 실제 설치 위치로 바꿔 입력하세요.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Dir "D:\SteamLibrary\steamapps\common\ProjectZomboid" -Zip .\pzopt-4a0e9546ec-classes.zip
```

### 설치 상태 확인

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Status
```

`installed: yes`와 `all files present and unchanged`가 표시되는지 확인합니다. 파일이 누락되거나 변경되면 `MISSING` 또는 `MODIFIED`로 표시됩니다.

### 설정 화면

Steam에서 게임을 실행한 뒤 메인 메뉴의 **PZ OPTIMIZATION** 항목을 엽니다. 게임 안에서 설정을 변경할 수 있으며, 일부 옵션은 게임을 다시 시작해야 적용됩니다.

### 제거

게임을 종료하고, 설치할 때 사용한 폴더에서 실행합니다.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Uninstall
```

게임 폴더를 직접 지정해야 한다면:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Dir "D:\SteamLibrary\steamapps\common\ProjectZomboid" -Uninstall
```

제거 후 다시 `-Status`를 실행해 `installed: no`를 확인할 수 있습니다. 설치할 때 생성되는 게임 폴더의 `Uninstall-PZ-Optimization.cmd`로도 제거할 수 있습니다.

## 3. Linux

압축 해제한 `pzopt-589f2f3f-discord` 디렉터리에서 실행합니다.

설치:

```bash
bash install.sh --zip pzopt-4a0e9546ec-classes.zip
```

설치 상태 확인:

```bash
bash install.sh --status
```

제거:

```bash
bash install.sh --uninstall
```

게임 폴더를 찾지 못하는 경우 `--dir`을 추가합니다.

```bash
bash install.sh --dir "$HOME/.local/share/Steam/steamapps/common/ProjectZomboid/projectzomboid" --zip pzopt-4a0e9546ec-classes.zip
```

배포판과 설치 형태에 따라 실제 경로가 다를 수 있습니다.

## 4. macOS

압축 해제한 `pzopt-589f2f3f-discord` 디렉터리에서 터미널을 실행합니다.

설치:

```bash
bash install.sh --zip pzopt-4a0e9546ec-classes.zip
```

설치 상태 확인:

```bash
bash install.sh --status
```

제거:

```bash
bash install.sh --uninstall
```

게임 폴더 검색에 실패하면 `--dir`로 **`projectzomboid.jar`가 들어 있는 디렉터리**를 지정하세요.

## 5. 파일 무결성 확인

GitHub Releases에 첨부된 외부 ZIP과 내부 설치 ZIP의 SHA-256은 서로 다릅니다. 아래 값과 비교해 주세요.

| 파일 | SHA-256 |
| --- | --- |
| `pzopt-589f2f3f.zip` | `c4ea4f9d8df03352f2f7e6a0ef24ca5bbda66ae6c42c77b7d2a5d3384ca66009` |
| `pzopt-4a0e9546ec-classes.zip` | `bd1ff13d83a2e8739ade95ec8ca8e32212b70c1f04a310803cc1432dc69a4e30` |

Windows PowerShell:

```powershell
Get-FileHash -Algorithm SHA256 -LiteralPath .\pzopt-4a0e9546ec-classes.zip
```

Linux:

```bash
sha256sum pzopt-4a0e9546ec-classes.zip
```

macOS:

```bash
shasum -a 256 pzopt-4a0e9546ec-classes.zip
```

해시가 다르면 설치하지 말고 파일을 다시 받으세요.

## 6. 설치 오류 및 주의사항

**게임 리비전이 맞지 않는다는 메시지가 나올 때**  
게임 버전을 확인하세요. `42.21`이라는 표기만 같다고 모든 내부 리비전에서 작동하는 것은 아닙니다. 설치 프로그램이 리비전 불일치를 감지하면 중단합니다.

**게임을 종료하라는 메시지가 나올 때**  
설치 프로그램은 게임 종료를 기다리도록 작성되어 있습니다. 설치 중에는 게임을 다시 실행하지 마세요.

**다른 Java 모드의 파일과 충돌할 때**  
두 모드가 같은 클래스 파일을 수정할 수는 없습니다. 설치 프로그램에 `-Force` 옵션이 있지만, 기존 파일을 별도 폴더로 이동할 수 있으므로 원인을 확인하기 전에는 사용하지 마세요.

**`classpath` 오류가 나올 때**  
`ProjectZomboid64.json`의 `classpath`에 `.`이 `projectzomboid.jar`보다 앞에 있어야 합니다. 기존에 AOT 또는 Java 관련 설정을 수정했다면 무작정 값을 바꾸지 말고 백업본과 현재 설정을 비교하세요.

**설정 파일을 직접 수정한 경우**  
`ProjectZomboid64.json`, `pzopt.properties` 등의 사용자 설정을 먼저 보관하세요. 설치 프로그램이 모든 개인 설정의 원상 복구를 보장하는 것은 아닙니다.

**업데이트 후 실행이 안 될 때**  
게임이 새 리비전으로 바뀌었는지 먼저 확인하세요. 기존 버전용 클래스 파일을 다른 게임 리비전에 억지로 적용하지 마세요.

**오류 제보 시 필요한 정보**  
게임 빌드/리비전, 운영체제, 그래픽카드, 모드 수, 재현 방법, 문제가 발생한 화면과 로그를 함께 전달해 주세요. Windows 기준 로그는 `%USERPROFILE%\Zomboid\console.txt`에 있습니다.
