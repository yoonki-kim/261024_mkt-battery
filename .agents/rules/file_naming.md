# Rule: File Naming Convention with Date Prefix

## Context & Requirement
README.md와 같이 관행적으로 표준화된 목적을 가진 파일을 제외한 모든 새로 생성되는 문서 및 프로젝트 파일은 파일명 앞에 생성일자 접두사(Prefix)를 붙여야 합니다.

## Format Specification
- **형식**: `YYMMDD_<파일명>.<확장자>`
- **예시**: `261024_makita_18v_battery_technical_spec.md`, `261024_power_circuit_design.md`
- **예외 대상**:
  - `README.md`
  - 표준 프로젝트 메타데이터/설정 파일 (`.gitignore`, `AGENTS.md`, `LICENSE` 등)

## Enforcement
- 에이전트가 `docs/` 또는 프로젝트 내에 새로운 분석 문서, 설계서, 사양서를 생성할 때는 항상 현재 날짜(YYMMDD)를 확인하고 접두사를 부여합니다.
- 기존 문서를 참조할 때도 변경된 명명 규칙을 적용하여 링크를 유지합니다.
