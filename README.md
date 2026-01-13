# Claude Code Utils

Claude Code에서 사용할 수 있는 스킬 모음입니다.

## 설치 방법

### 방법 1: Template으로 새 프로젝트 시작 (추천)

1. GitHub 저장소 Settings에서 **Template repository** 체크
2. 새 프로젝트 시작 시 "Use this template" 클릭
3. 새 저장소 이름 입력 후 생성
4. Clone해서 사용

```bash
git clone https://github.com/YourUsername/new-project.git
cd new-project
```

### 방법 2: 기존 프로젝트에 복사

```bash
cd /path/to/your-project
cp -r /path/to/claude-code-utils/.claude .
```

### 방법 3: 글로벌 설치

모든 프로젝트에서 사용하려면 홈 디렉토리에 복사:

```bash
cp -r /path/to/claude-code-utils/.claude ~/.claude
```

> 로컬(`./.claude`)과 글로벌(`~/.claude`) 둘 다 있으면 로컬이 우선

---

## GSD (Get Shit Done) 스킬

프로젝트를 체계적으로 관리하기 위한 스킬 시스템입니다.

### 주요 커맨드

| 커맨드 | 설명 |
|--------|------|
| `/gsd:help` | 도움말 보기 |
| `/gsd:new-project` | 새 프로젝트 초기화 |
| `/gsd:map-codebase` | 코드베이스 구조 분석 |
| `/gsd:create-roadmap` | 로드맵 생성 |
| `/gsd:new-milestone` | 마일스톤 생성 |
| `/gsd:discuss-milestone` | 마일스톤 요구사항 논의 |
| `/gsd:plan-phase` | 단계별 계획 수립 |
| `/gsd:research-phase` | 구현 전 조사 |
| `/gsd:execute-plan` | 계획 실행 |
| `/gsd:verify-work` | 작업 검증 |
| `/gsd:status` | 현재 상태 확인 |
| `/gsd:progress` | 진행률 보기 |
| `/gsd:pause-work` | 작업 일시정지 (컨텍스트 저장) |
| `/gsd:resume-work` | 작업 재개 |
| `/gsd:complete-milestone` | 마일스톤 완료 |

### 전체 커맨드 목록

```
/gsd:add-phase          /gsd:add-todo           /gsd:check-todos
/gsd:complete-milestone /gsd:consider-issues    /gsd:create-roadmap
/gsd:discuss-milestone  /gsd:discuss-phase      /gsd:execute-phase
/gsd:execute-plan       /gsd:help               /gsd:insert-phase
/gsd:list-phase-assumptions                     /gsd:map-codebase
/gsd:new-milestone      /gsd:new-project        /gsd:pause-work
/gsd:plan-fix           /gsd:plan-phase         /gsd:progress
/gsd:remove-phase       /gsd:research-phase     /gsd:resume-task
/gsd:resume-work        /gsd:status             /gsd:verify-work
```

---

## 사용 시나리오

### 1. 새 프로젝트 시작

```
/gsd:new-project        # 프로젝트 정의
/gsd:create-roadmap     # 로드맵 생성
/gsd:new-milestone      # 첫 마일스톤 생성
```

### 2. 기존 프로젝트에 GSD 적용

```
/gsd:map-codebase       # 코드베이스 분석
/gsd:new-project        # 프로젝트 정의
```

### 3. 일반적인 개발 흐름

```
/gsd:plan-phase         # 계획 수립
/gsd:execute-plan       # 코드 작성
/gsd:verify-work        # 검증
/gsd:complete-milestone # 마일스톤 완료
```

### 4. 작업 중단/재개

```
/gsd:pause-work         # 오늘 작업 끝, 컨텍스트 저장
# ... 다음 날 ...
/gsd:resume-work        # 어디까지 했는지 파악하고 이어서 작업
```

---

## 폴더 구조

```
프로젝트/
├── .claude/              # 스킬 정의 (이 저장소에서 복사됨)
│   ├── commands/gsd/     # 슬래시 커맨드
│   ├── get-shit-done/    # 워크플로우, 템플릿, 참고문서
│   └── settings.local.json
│
├── .gsd/                 # 프로젝트 상태 (GSD가 자동 생성)
│   ├── project.md
│   ├── roadmap.md
│   ├── state.md
│   └── milestones/
│
└── src/                  # 실제 코드
```

- **`.claude/`**: 스킬 정의 파일들 (수정 안 함)
- **`.gsd/`**: GSD가 관리하는 프로젝트 상태 (자동 생성)

---

## 스킬 업데이트

Template으로 생성한 프로젝트는 원본과 동기화되지 않습니다.
새 스킬이 추가되면 수동으로 가져와야 합니다:

```bash
# 특정 파일만 복사
cp /path/to/claude-code-utils/.claude/commands/gsd/new-skill.md \
   /path/to/my-project/.claude/commands/gsd/

# 또는 전체 덮어쓰기
cp -r /path/to/claude-code-utils/.claude ./
```
