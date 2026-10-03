# Project Starter Kit

개인 프로젝트를 기본으로, 필요한 에이전트 지침과 GitHub 양식을 골라 적용하는 템플릿 모음입니다. 템플릿 원본은 `templates/common/`에 보관하고, 이 저장소 루트에는 적용용 `AGENTS.md`, `CLAUDE.md`, `.github/`를 두지 않습니다.

## 구성

| 템플릿 | 용도 |
| --- | --- |
| [AGENTS.md](templates/common/AGENTS.md) | 프로젝트 설정, 작업·문체·검증·Git·이슈·PR 규칙 |
| [CLAUDE.md](templates/common/CLAUDE.md) | 공통 지침을 가져오는 `@AGENTS.md` |
| [.gitattributes](templates/common/.gitattributes) | 선택적으로 도입하는 텍스트 줄바꿈 규칙 |
| [결함 보고](templates/common/.github/ISSUE_TEMPLATE/bug.yml) | 현재·기대 동작, 재현 근거와 환경 |
| [기능·개선 제안](templates/common/.github/ISSUE_TEMPLATE/change.yml) | 현재·목표 상태, 최소 변경과 완료 조건 |
| [부모 이슈](templates/common/.github/ISSUE_TEMPLATE/parent.yml) | 직접 자식의 결과·선행 관계·통합 완료 조건 |
| [질문·사용 문의](templates/common/.github/ISSUE_TEMPLATE/question.yml) | 사용 상황과 확인한 자료 |
| [이슈 선택 설정](templates/common/.github/ISSUE_TEMPLATE/config.yml) | 빈 이슈 허용 여부와 외부 문의 경로 |
| [PR 템플릿](templates/common/.github/pull_request_template.md) | 요약·변경·완료 조건·검증·남은 문제 |

## 필요한 구성 선택

별도 프로필 파일이나 생성기 없이 아래 기준으로 선택합니다. 기존 팀 규칙이 있으면 해당 규칙을 보존합니다.

| 용도 | 복사할 파일 |
| --- | --- |
| 에이전트 작업 지침 | `AGENTS.md`, `CLAUDE.md`를 함께 복사 |
| 기본 GitHub 협업 | `bug.yml`, `change.yml`, `config.yml`, PR 템플릿 |
| 여러 구현 이슈를 묶는 작업 | 기본 구성에 `parent.yml` 추가 |
| 저장소에서 사용 문의 접수 | `question.yml` 추가 |
| 줄바꿈 규칙 통일 | 기존 설정을 확인한 뒤 `.gitattributes` 병합 |

GitHub 양식만 필요하면 선택한 `.github/` 파일만 복사해도 됩니다. 질문을 외부에서 받으려면 `config.yml`의 `contact_links` 예시를 실제 경로로 바꿉니다. 빈 이슈를 허용하려면 `blank_issues_enabled`를 `true`로 바꿉니다.

## 처음 적용

1. 사용할 원본의 tag 또는 commit을 정합니다.
2. 선택한 파일을 **대상 프로젝트 루트**에 같은 상대 경로로 복사합니다. `templates/common` 폴더 자체를 옮기는 것이 아닙니다. 숨김 파일·폴더도 포함합니다.
3. 대상에 이미 있는 파일은 내용을 비교해 병합합니다. 특히 기존 `AGENTS.md`, GitHub 설정과 줄바꿈 규칙을 일괄 덮어쓰지 않습니다.
4. `AGENTS.md`의 `미설정`을 실제 값·문서 링크 또는 `해당 없음`으로 채웁니다. 명령은 프로젝트 manifest·스크립트·README에서 확인하고 실행 위치·전제 조건을 적습니다.
5. `AGENTS.md`의 언어·브랜치·문체 기본값을 확인합니다. 바꾸는 항목은 관련 양식도 함께 맞춥니다.
6. 원본 저장소·tag 또는 commit·선택한 파일을 `AGENTS.md`의 프로젝트 설정 표에 적습니다. GitHub 양식만 복사하면 README 등 기존 문서 한 곳에 기록합니다.
7. diff를 확인하고 프로젝트의 필요한 검사를 수행합니다. 기본 브랜치 반영 후 실제 이슈 선택 화면과 PR 본문도 확인합니다.

```text
my-project/
├── AGENTS.md
├── CLAUDE.md
├── .gitattributes                  # 선택
└── .github/
    ├── ISSUE_TEMPLATE/
    │   ├── bug.yml
    │   ├── change.yml
    │   ├── parent.yml             # 선택
    │   ├── question.yml           # 선택
    │   └── config.yml
    └── pull_request_template.md
```

이 저장소를 복제하거나 GitHub의 "Use this template"로 생성해도 위 적용 단계가 필요합니다. 템플릿 폴더는 그대로 복제되며 GitHub가 그 안의 양식을 자동 적용하지 않습니다.

## 원본을 갱신할 때

복사본은 자동 동기화되지 않습니다. 기록한 이전 원본과 새 원본의 차이를 먼저 보고, 대상 프로젝트에 필요한 변경만 기존 수정과 병합합니다. 프로젝트 설정값·직접 추가한 규칙·뺀 선택 항목을 보존하고 적용 기록과 검증 결과를 갱신합니다.

이전 원본을 모르면 그 상태를 기록하고 현재 파일별로 비교합니다. 같은 버전을 다시 검토할 때 중복 항목을 추가하지 않습니다. 자동 병합·배포·원격 저장소 설정 변경 도구는 포함하지 않습니다.

## 문서 읽기와 문체

- 작업·검증·Git·이슈·PR 규칙은 `AGENTS.md` 한 곳에 둡니다. 프로젝트 동작에 필요한 추가 문서만 일반 링크로 연결합니다.
- `CLAUDE.md`는 `@AGENTS.md`로 공통 규칙을 가져옵니다. 규칙을 두 파일에 중복 작성하지 않습니다. [Claude import 문서](https://code.claude.com/docs/en/memory#import-additional-files)
- 기본 언어는 한국어, 새 브랜치는 `feature/`, PR·커밋 제목은 Conventional Commit 형식입니다. 이 값은 팀 취향이며 기술 스택과 무관한 필수 규격은 아닙니다.
- 앰대시·엔대시를 피하는 문체 기준과 예외는 `AGENTS.md` 한 곳에서 관리합니다.
- 제품 동작의 기준은 담당 코드·문서에 둡니다. README는 사람용 개요·설치·사용 방법을 담당합니다.

## 작업 분할과 완료 조건

독립적으로 끝낼 결과는 구현 이슈로 나누고 공통 목표가 있으면 부모로 묶습니다. 하나의 완료 조건을 여러 PR로 구현할 때는 같은 이슈에서 진행 표를 관리합니다. PR 개수만으로 부모를 만들지 않습니다.

중간 PR은 `Refs`, 전체 완료 조건을 충족하는 최종 PR은 `Closes`를 사용합니다. 부모는 자식의 종료 사유와 통합 결과까지 확인하고 따로 닫습니다. 관련 규칙은 [AGENTS.md](templates/common/AGENTS.md)를 따릅니다. [GitHub 이슈 연결 규칙](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)

PR에는 기본 필수 항목 6개만 표시합니다. 분할·호환성·측정·독립 검토·base 변경의 상세 내용은 해당할 때 기존 항목에 추가합니다. 필수 항목을 바꾸면 AGENTS.md와 PR 템플릿도 함께 맞춥니다.

## 템플릿 수정 시 확인

- 변경한 문서의 링크와 양식 항목이 서로 맞는지 확인합니다.
- diff를 확인하고, 대상 저장소에 적용한 뒤 실제 이슈 선택 화면과 PR 본문을 확인합니다. [GitHub 폼 스키마](https://docs.github.com/en/communities/using-templates-to-encourage-useful-issues-and-pull-requests/syntax-for-githubs-form-schema)

## 줄바꿈

유지보수 저장소 자체는 LF를 사용하고, 복사용 `.gitattributes`는 `text=auto`만 기본으로 둡니다. 프로젝트에 필요한 LF·CRLF 규칙은 주석 예시에서 선택합니다. Windows 배치 파일(`.bat`, `.cmd`)과 기존 예외 규칙도 확인합니다. [GitHub 줄바꿈 가이드](https://docs.github.com/en/get-started/git-basics/configuring-git-to-handle-line-endings)

기존 저장소에 줄바꿈 규칙을 도입하면 정규화 diff가 생길 수 있습니다. 진행 중인 변경을 먼저 보존하고 작업 트리가 깨끗한지 확인한 뒤 `git add --renormalize .`의 결과를 검토해 정규화 변경을 별도 커밋으로 분리합니다.

공개 배포 전에는 코드와 복사되는 템플릿의 라이선스를 정해야 합니다. 이 세트는 대상 프로젝트의 라이선스를 선택하거나 바꾸지 않습니다.
