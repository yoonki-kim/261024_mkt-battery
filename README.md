# Makita 18V Battery Applications Project

마키타(Makita) 18V LXT 호환 리튬이온 배터리를 주 전원으로 활용하는 다양한 하드웨어 및 임베디드 응용 기기 개발 프로젝트입니다.

---

## 📌 프로젝트 개요

- **공칭 전압**: 18.0V (5S2P 리튬이온 셀 구성)
- **완충 / 방전 종지 전압**: 21.0V / 14.0V~15.0V
- **주요 응용 개발 대상**:
  - 고출력 USB-PD 파워뱅크 (65W/100W 양방향 모듈)
  - 12V 차량용/아웃도어 전원 공급기 (High-power Buck Converter)
  - 고휘도 LED 작업등/캠핑 랜턴 (PWM 디밍 제어)
  - DC 모터 및 로봇 파워트레인 드라이버
  - 휴대용 220V 인버터 스테이션

---

## 📚 프로젝트 문서

- **[배터리 기술 사양서](docs/261024_makita_18v_battery_technical_spec.md)**: 알리익스프레스 구매 배터리 상세 스펙, 핀아웃, 전기적 특성 및 저전압 차단(LVD) 회로 설계 가이드라인
- **[USB & Type-C 어댑터 기술 사양서](docs/261024_makita_usb_type_c_adapter_technical_spec.md)**: 알리익스프레스 구매 USB/Type-C 양방향 충방전 어댑터 스펙, 내부 보호 회로 및 활용 방안
- **[프로젝트 작업 이력서](docs/261024_work_history.md)**: 작업 세션별 진행 내역, 결정 사항, 파일 트리 및 향후 로드맵
- **[문서 인덱스](docs/README.md)**: `docs/` 디렉터리 문서 안내
- **[프로젝트 규칙 및 메모리](AGENTS.md)**: AI 에이전트 작업 지침 및 파일 명명 규칙
