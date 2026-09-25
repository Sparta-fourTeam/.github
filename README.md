## 개발 환경 설정

이 저장소는 [pre-commit](https://pre-commit.com/)으로 커밋 전에 코드 검사를 자동으로 실행합니다.
`git clone`만으로는 Git 훅이 설치되지 않으니, **클론한 뒤 각자 한 번씩 `pre-commit install`을 실행해 주세요.**

### 1. pre-commit 설치

사용하는 환경에 맞는 방법 하나를 고르세요.

**macOS (Homebrew)**
```bash
brew install pre-commit
```

**pip (Python 3.8 이상)**
```bash
pip install pre-commit
# 또는 전역 환경을 건드리지 않으려면
pipx install pre-commit
```

설치 확인:
```bash
pre-commit --version
```

### 2. 저장소 클론

```bash
git clone (레포 주소)
```

### 3. Git 훅 설치

```bash
pre-commit install
```

`pre-commit installed at .git/hooks/pre-commit` 메시지가 나오면 완료입니다.
이제 `git commit`을 할 때마다 `.pre-commit-config.yaml`에 정의된 검사가 자동으로 실행됩니다.

### 4. (선택) 전체 파일 한 번 검사하기

훅은 기본적으로 **이번 커밋에서 변경된 파일**만 검사합니다. 처음 설정한 뒤 전체 파일을 한 번 점검하려면:

```bash
pre-commit run --all-files
```

### 문제 해결

- **검사에 실패해 커밋이 막혔을 때**: 출력된 오류를 수정하고 다시 `git add` → `git commit` 하세요. 포매터가 파일을 자동으로 고친 경우에도 수정된 파일을 다시 `git add` 해야 합니다.
- **훅 버전 업데이트**: `pre-commit autoupdate`
- **긴급하게 검사를 건너뛰어야 할 때**: `git commit --no-verify` (가급적 사용하지 마세요)
