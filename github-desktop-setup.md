# GitHub Desktop 설치 및 초기 셋팅 가이드 (Windows)

## 1. 설치

### 방법 A: winget (권장, PowerShell 관리자 권한)
```powershell
winget install --id GitHub.GitHubDesktop -e --source winget
# Git CLI도 함께 쓰려면
winget install --id Git.Git -e --source winget
```

### 방법 B: 수동 설치
1. https://desktop.github.com 접속 → **Download for Windows**
2. `GitHubDesktopSetup-x64.exe` 실행 (사용자 단위 설치, 관리자 권한 불필요)

## 2. 로그인
1. GitHub Desktop 실행 → **Sign in to GitHub.com**
2. 브라우저에서 GitHub 계정 로그인 → **Authorize desktop** 클릭
3. 앱으로 자동 복귀 확인

## 3. Git 사용자 정보 설정
- 메뉴: **File → Options → Git**
  - Name: `<GIT_USER_NAME>`
  - Email: `<GIT_USER_EMAIL>` (GitHub 개인정보 보호 시 `<ID>+<USERNAME>@users.noreply.github.com`)
- 기본 브랜치명: `main`

CLI로 동일하게 설정하려면:
```bash
git config --global user.name  "<GIT_USER_NAME>"
git config --global user.email "<GIT_USER_EMAIL>"
git config --global init.defaultBranch main
git config --global core.autocrlf true   # Windows 줄바꿈 처리
```

## 4. 저장소 Clone (`sub979/aws-certfi`)
1. **File → Clone repository** (`Ctrl+Shift+O`)
2. **GitHub.com** 탭 → `sub979/aws-certfi` 선택
3. Local path: `C:\work\aws-certfi` (경로에 한글/공백 지양)
4. **Clone** 클릭

## 5. 권장 옵션
| 항목 | 위치 | 권장값 |
|------|------|--------|
| 외부 에디터 | Options → Integrations | Visual Studio Code |
| 셸 | Options → Integrations | PowerShell 또는 Git Bash |
| 다크 모드 | Options → Appearance | 선택 |
| 커밋 전 확인 | Options → Prompts | 강제 푸시/브랜치 삭제 확인 ON |

## 6. 기본 작업 흐름
1. **Current branch → New branch** 로 작업 브랜치 생성
2. 파일 수정 → 좌측 **Changes** 에서 변경 확인
3. Summary 입력 → **Commit to `<BRANCH>`**
4. **Publish branch / Push origin**
5. **Create Pull Request** → 브라우저에서 PR 생성

## 7. 트러블슈팅
| 증상 | 조치 |
|------|------|
| 로그인 후 앱 복귀 안 됨 | 브라우저 팝업 차단 해제 후 재시도 |
| 사내 프록시 환경 접속 실패 | `git config --global http.proxy http://<PROXY_HOST>:<PROXY_PORT>` |
| SSL 인증서 오류 (사내 CA) | `git config --global http.sslCAInfo "<CA_BUNDLE_PATH>"` (SSL 검증 비활성화 금지) |
| 인증 만료 | File → Options → Accounts → Sign out 후 재로그인 |
