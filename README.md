# kevin-planning-skill

코드를 고치기 전에 개발 계획서부터 쓰게 하는 Claude Code 스킬(`planning`)입니다.
계획서는 9개 장으로 된 정해진 틀을 따르고, 확인한 사실과 추정을 나눠 적습니다.

## 들어 있는 것

```
planning/
├── SKILL.md   스킬 본문. 계획서를 쓰는 순서와 하지 않는 것
└── rules.md   계획서 작성 규칙. 9개 장 구성, 장별 작성 원칙, 승인 표, 용어 규칙
```

## 설치

스킬 폴더를 Claude Code 전역 스킬 위치에 복사합니다.

macOS · Linux · Git Bash:

```bash
git clone https://github.com/Eumhongin/kevin-planning-skill.git
cp -r kevin-planning-skill/planning ~/.claude/skills/
```

Windows PowerShell:

```powershell
git clone https://github.com/Eumhongin/kevin-planning-skill.git
Copy-Item -Recurse kevin-planning-skill\planning "$env:USERPROFILE\.claude\skills\"
```

Claude Code 를 다시 켜면 스킬 목록에 `planning` 이 보입니다.

## 쓰는 법

Claude Code 에 「계획서 써줘」, 「계획 세워줘」라고 하거나 `/planning` 을 입력합니다.
코드 작업을 시켰는데 계획서가 없으면 스킬이 계획서부터 씁니다.

## 어느 규칙을 따르나

1. 작업 중인 프로젝트에 `.claude/rules/plan.md` 가 있으면 그 파일을 따릅니다.
2. 없으면 스킬 폴더의 `rules.md` 를 따릅니다.

프로젝트마다 규칙을 다르게 두고 싶으면 `rules.md` 를 복사해 그 프로젝트의 `.claude/rules/plan.md` 로 두고 고칩니다.

## 계획서 구성

| 장 | 쓰는 것 |
| --- | --- |
| 1. 배경 및 목적 | 지금 무엇이 문제인지. 비개발자도 읽는 평문 |
| 2. 개선 사항 요약 | 「~문제가 있어서, ~합니다」 한 문장씩 |
| 3. 개선 상세 | 현재 동작·문제점·변경 내용·검증 방법·근거 |
| 4. 수정 범위 | 바꾸는 파일과 영향, 이번에 하지 않는 것 |
| 5. 테스트 계획 | 테스트 구성·시나리오·통과 기준 |
| 6. 리스크 및 대응 방안 | 예상 위험과 대응 |
| 7. 단계별 실행 계획 | Phase 별 체크리스트 |
| 8. 완료 기준 | 계획 전체가 끝났다고 말할 조건 |
| 9. 참고 자료 (References) | 본문 `[n]` 번호의 출처 |

## 알아 둘 것

- 작성자 환경에 맞춘 스킬입니다. 계획서와 문장은 한국어 `~합니다` 체로 씁니다.
- `SKILL.md` 가 가리키는 `~/.claude/rules/git.md`(브랜치 규칙)와 「헌법」은 작성자의 개인 규칙 파일이라 이 저장소에 없습니다. 없으면 그 줄은 건너뛰거나 자기 규칙으로 바꿔 쓰세요.
- 승인 표의 「케빈님 승인」은 계획을 승인하는 사람을 뜻합니다. 자기 이름이나 역할로 바꿔 쓰세요.

## 라이선스

MIT. [LICENSE](LICENSE) 를 봅니다.
