# Claude TDD 템플릿

LLM 기반 개발, 특히 Claude Code를 위해 설계된 Kent Beck의 테스트 주도 개발(TDD) 및 Tidy First 원칙을 적용하기 위한 GitHub 템플릿입니다.

## 개요

이 템플릿은 Claude를 페어 프로그래밍 파트너로 하여 TDD 개발을 위한 구조화된 워크플로우를 제공합니다. 커스텀 슬래시 커맨드와 전문화된 스킬을 통해 엄격한 TDD 규율을 적용하며, 코드 변경이 Red-Green-Refactor 사이클을 따르고 구조적 변경과 행동적 변경 사이의 분리를 유지하도록 보장합니다.

**크레딧**: 이것은 Kent Beck의 B+ Tree 구현에서 가져온 [Kent Beck의 CLAUDE.md](https://github.com/KentBeck/BPlusTree3/blob/ca80e4d85a99cd0af2effe717f709d43e80403bc/rust/docs/CLAUDE.md)를 기반으로 합니다. 이 템플릿은 그의 방법론을 실용적인 Claude Code 스킬과 커맨드로 확장합니다.

## 핵심 방법론

템플릿은 다음과 같은 핵심 원칙을 적용합니다:

- **Red → Green → Refactor**: 항상 TDD 사이클을 따릅니다
- **Tidy First**: 구조적 변경과 행동적 변경을 분리합니다
- **한 번에 하나의 테스트**: 하나의 실패하는 테스트를 작성하고, 통과시킨 후, 구조를 개선합니다
- **커밋 규율**: 모든 테스트가 통과하고 변경이 논리적으로 완료된 경우에만 커밋합니다
- **작은 단계**: 테스트를 통과시키기 위한 가능한 가장 작은 변경을 수행합니다

## 기능

### 슬래시 커맨드

- `/go` - TDD 사이클 시작: PLAN.md에서 다음 테스트를 찾아 구현
- `/red` - 실패하는 테스트 작성 (RED 단계)
- `/green` - 테스트를 통과시키기 위한 최소 코드 구현 (GREEN 단계)
- `/refactor` - 테스트를 그린 상태로 유지하면서 코드 구조 개선
- `/tidy` - 동작을 변경하지 않고 구조적 변경 수행 (Tidy First)
- `/tdd-cycle` - 완전한 RED → GREEN → REFACTOR 사이클 실행
- `/fix-defect` - TDD 접근 방식으로 버그 수정
- `/next-test` - PLAN.md에서 다음 미완료 테스트 표시
- `/run-tests` - 모든 테스트 실행 (장시간 실행되는 테스트 제외)
- `/commit-tidy` - 구조적 변경 커밋
- `/commit-behavior` - 행동적 변경 커밋

### 스킬

#### TDD 워크플로우 스킬
- **tdd-go** - 메인 TDD 워크플로우 자동화
- **tdd-red** - RED 단계: 실패하는 테스트 작성
- **tdd-green** - GREEN 단계: 최소 코드로 테스트 통과
- **tdd-refactor** - REFACTOR 단계: 코드 구조 개선
- **tdd-cycle** - 완전한 TDD 사이클 오케스트레이션
- **tdd-tidy** - Tidy First 구조적 개선

#### 개발 지원 스킬
- **code-reviewer** - 품질 검사를 포함한 철저한 코드 리뷰
- **git-committer** - 규칙을 따르는 잘 구조화된 커밋 생성
- **pull-request-descriptor** - 포괄적인 PR 설명 생성
- **prompt-enhancer** - 프로젝트 컨텍스트로 프롬프트 향상
- **skill-creator** - 새로운 커스텀 스킬 생성

## 빠른 시작

1. **이 템플릿을 사용**하여 새 저장소 생성
2. 테스트/기능을 나열한 **PLAN.md 파일 생성**
3. 테스트 설명 언어를 지정하는 **LANG.md 파일 생성** (예: "Korean", "English")
4. **`/go` 실행**하여 TDD 사이클 시작

### PLAN.md 예제

```markdown
# 테스트 계획

- [ ] 사용자가 계정을 생성할 수 있다
- [ ] 사용자가 유효한 자격 증명으로 로그인할 수 있다
- [ ] 사용자가 유효하지 않은 자격 증명으로 로그인할 수 없다
- [ ] 사용자가 비밀번호를 재설정할 수 있다
```

### 워크플로우 예제

```bash
# 다음 테스트에 대한 TDD 사이클 시작
/go

# 또는 각 단계를 수동으로 제어
/red          # 실패하는 테스트 작성
/green        # 최소 코드 구현
/refactor     # 구조 개선
```

## 작동 방식

1. **계획**: PLAN.md에 테스트 정의
2. **RED 단계**: Claude가 다음 미완료 항목에 대한 실패하는 테스트 작성
3. **GREEN 단계**: Claude가 테스트를 통과시키기 위한 최소 코드 구현
4. **REFACTOR 단계**: Claude가 테스트를 그린 상태로 유지하면서 코드 구조 개선
5. **커밋**: 구조적(Tidy) 변경과 행동적 변경을 별도로 커밋
6. **반복**: PLAN.md의 다음 테스트로 이동

## 파일 구조

```
.claude/
├── commands/           # TDD 워크플로우를 위한 슬래시 커맨드
│   ├── go.md
│   ├── red.md
│   ├── green.md
│   ├── refactor.md
│   └── ...
├── skills/            # Claude Code 스킬
│   ├── tdd-go/
│   ├── tdd-red/
│   ├── tdd-green/
│   ├── code-reviewer/
│   └── ...
CLAUDE.md              # Claude를 위한 주요 지침
PLAN.md               # 테스트 계획 (생성 필요)
LANG.md               # 테스트 설명 언어 (생성 필요)
```

## 이점

- **규율 있는 개발**: TDD 모범 사례를 자동으로 적용
- **깨끗한 커밋**: 구조적 변경과 행동적 변경 분리
- **품질 보증**: 커밋 전 모든 테스트 통과 필수
- **문서화**: PLAN.md가 로드맵과 문서 역할을 동시에 수행
- **재현 가능**: 다양한 프로젝트와 언어에 걸쳐 동일한 방법론 적용

## 더 알아보기

- [Kent Beck의 원본 CLAUDE.md](https://github.com/KentBeck/BPlusTree3/blob/ca80e4d85a99cd0af2effe717f709d43e80403bc/rust/docs/CLAUDE.md)
- [Test-Driven Development: By Example](https://www.amazon.com/Test-Driven-Development-Kent-Beck/dp/0321146530)
- [Tidy First?](https://www.oreilly.com/library/view/tidy-first/9781098151232/)
