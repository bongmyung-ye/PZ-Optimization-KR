# PZ Optimization — 한국어 배포 안내

프로젝트 좀보이드용 최적화 모드 **PZ Optimization**의 `589f2f3f` 테스트 빌드를 한국어로 안내하는 비공식 배포 저장소입니다.

모드 개발자는 **xD3I**입니다. 이 저장소는 제작자의 재배포 허락을 바탕으로 운영하며, 모드 자체를 수정하거나 별도로 개발한 버전은 제공하지 않습니다.

- 원본 프로젝트: [xD3I/PZ_Optimization](https://github.com/xD3I/PZ_Optimization)
- 배포 출처: PZ Optimization 공식 Discord `#pre-release-testing` (2026년 10월 26일)
- 테스트 빌드: `589f2f3f`
- 게임: Project Zomboid Build **42.21**, 리비전 **`4a0e9546ec`**
- 운영체제: Windows, Linux, macOS

> **테스트 빌드 안내**  
> 이번 파일은 제작자가 Discord에 공개한 사전 테스트용 빌드이며, 정식 안정판이 아닙니다. 게임 빌드 번호가 같아도 내부 리비전이 다르면 설치할 수 없습니다. 플레이 중인 저장 파일은 따로 백업한 뒤 사용하세요.

## 다운로드

저장소의 **Releases**에서 `589f2f3f-test` 릴리스를 열고 `pzopt-589f2f3f.zip`을 받으면 됩니다. GitHub의 `Source code (zip)`은 모드 설치 파일이 아닙니다.

다운로드한 파일은 압축을 풀어 사용합니다. 폴더 안에 `install.ps1`, `install.sh`, `pzopt-4a0e9546ec-classes.zip`이 있는지 확인하세요.

## Windows 설치

1. 게임과 실행 중인 좀보이드 서버를 종료합니다. 서버가 별도로 실행 중이라면 서버 파일은 건드리지 마세요.
2. 다운로드한 ZIP을 압축 해제하고 `pzopt-589f2f3f-discord` 폴더를 엽니다.
3. 탐색기 주소창에 `powershell`을 입력해 해당 폴더에서 PowerShell을 엽니다.
4. 아래 명령을 실행합니다.

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Zip .\pzopt-4a0e9546ec-classes.zip
```

설치 상태 확인:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Status
```

제거:

```powershell
powershell -NoProfile -ExecutionPolicy Bypass -File .\install.ps1 -Uninstall
```

게임 폴더를 찾지 못하는 경우와 Linux/macOS 설치법은 [설치 및 제거 안내](INSTALL.md)를 참고하세요.

## 이번 빌드에서 달라진 점

- 모드 Lua 이벤트 처리 및 저장 파일 불러오기 개선
- 좀비·맵 청크 관련 모드 처리 조정
- PZ Optimization 설정 화면 개편 및 벤치마크 항목 추가
- 컨트롤러 입력과 화면 키보드 반응 개선
- 나무, 지형, 잔디 관련 화면 깜빡임 수정
- Lua 컴파일러, 광원 그림자, 수면 반사, 지형·잔디 기능 추가(기본값 꺼짐)

설정별 변경 사항과 테스트 항목은 [변경 내역 및 테스트 안내](CHANGES.md)에서 확인할 수 있습니다.

## 설치 전에 확인할 점

- **게임 리비전 확인:** 설치 프로그램은 게임과 배포 파일의 리비전을 비교합니다. 일치하지 않으면 설치하지 않습니다.
- **기존 설치:** 같은 게임 폴더에 설치된 PZ Optimization 파일은 교체될 수 있습니다.
- **Java 모드 충돌:** 동일한 게임 클래스 파일을 사용하는 다른 모드가 있으면 설치 프로그램이 중단될 수 있습니다. 원인을 모르는 상태에서 `-Force` 옵션을 사용하지 마세요.
- **설정 파일:** 설치 과정에서 게임 폴더의 파일이 변경됩니다. `ProjectZomboid64.json`을 직접 수정한 적이 있다면 먼저 백업하세요.
- **별도 번역 패치:** 한국어 번역 패치는 PZ Optimization 설치 파일과 구분해서 관리합니다. 이 저장소의 ZIP에 한국어 패치가 포함된 것은 아닙니다.

## 파일 검증

외부 배포 ZIP의 SHA-256:

```text
c4ea4f9d8df03352f2f7e6a0ef24ca5bbda66ae6c42c77b7d2a5d3384ca66009
```

내부 설치 ZIP의 SHA-256(제작자 README에 기재된 값과 일치):

```text
bd1ff13d83a2e8739ade95ec8ca8e32212b70c1f04a310803cc1432dc69a4e30
```

검증 방법은 [설치 및 제거 안내](INSTALL.md#파일-무결성-확인)와 [`SHA256SUMS.txt`](SHA256SUMS.txt)를 참고하세요.

## 오류 제보

문제가 발생했다면 게임 빌드와 리비전, 운영체제, 그래픽카드, 활성화한 모드 수, 문제가 발생한 시점과 재현 방법을 함께 남겨주세요. 가능하면 `%USERPROFILE%\Zomboid\console.txt`의 관련 로그도 첨부해 주세요.

모드 오류는 원본 프로젝트 및 공식 Discord의 버그 제보 채널에 알려주는 것이 가장 정확합니다.

## 출처 및 권리

PZ Optimization의 원저작자 및 개발자는 **xD3I**입니다. 이 저장소는 한국어 안내와 재배포 파일을 구분해서 관리합니다. 원본 모드에 새로운 라이선스를 부여하지 않으며, 제작자의 공식 릴리스를 대체하는 저장소도 아닙니다.
