# Makita 18V Battery Applications Documentation

이 디렉터리는 AliExpress에서 구매한 마키타(Makita) 18V LXT 호환 배터리를 주 전원으로 활용하는 다양한 하드웨어 및 임베디드 어플리케이션 프로젝트의 기술 문서들을 보관합니다.

---

## 📑 문서 목록

1. **[마키타 18V LXT 호환 배터리 기술 사양서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md)**
   - 배터리 기본 전기적 특성 (공칭 18V, 완충 21V, 방전 종지 15V)
   - 5S2P 셀 구성 및 용량 분석
   - 메인 블레이드 단자(+, -, TH) 및 옐로우 통신 커넥터 핀아웃
   - BMS 보호 회로 및 DIY 프로젝트 시 필수 **저전압 차단(LVD)** 요구사항
   - LED 잔량 표시계 동작 특성 및 충전 가이드라인
2. **[마키타 18V 배터리용 USB & Type-C 충전 어댑터 기술 사양서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_usb_type_c_adapter_technical_spec.md)**
   - 알리익스프레스 구매 정보 및 제품 외형 분석
   - USB-A (5V/2.1A) 및 Type-C 양방향 충방전(5V/2A 출력 및 5V/9V 입력 승압 충전) 스펙
   - 마키타 배터리 파워뱅크화 및 임베디드 장비 전원 공급 활용 방안
   - 내장 저전압 차단(LVD) 보호 및 엔지니어링 주의점
3. **[프로젝트 작업 이력서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_work_history.md)**
   - 프로젝트 착수 이후의 모든 작업 이력, 기술 분석 결과, 파일 트리 및 향후 작업 계획 기록
   - 신규 세션 시작 시 최우선 컨텍스트 복원용 문서

---

## 🚀 향후 개발 예정 어플리케이션 후보

- [ ] **고출력 USB-PD 충전기/파워뱅크** (USB-C 65W/100W 양방향 모듈)
- [ ] **12V 차량용 및 캠핑용 전원 공급기** (18V to 12V High-power Buck Converter)
- [ ] **휴대용 고휘도 작업등/캠핑 랜턴** (PWM 디밍 제어)
- [ ] **모바일 로봇 / DC 모터 구동 파워 트레인**
- [ ] **휴대용 220V 소형 인버터 스테이션**
