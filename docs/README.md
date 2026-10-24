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
2. **[마키타 18V 배터리 정품 vs 가품 구별 가이드](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_battery_genuine_vs_counterfeit_guide.md)**
   - 외관 5대 포인트: 전자저울 무게 실측, LED 확산 렌즈(면발광), 나사 봉인 캡, 스타 마크(★), 바닥 각인 방향
   - 순정 급속 충전기(DC18RC) 1-Wire 통신 및 쿨링팬 반응
   - 분해 시 내부 셀(Sony/Murata vs 중국산) 및 기판 실리콘 포팅 비교
   - 오픈마켓 시세 및 위조품 방지 팁
3. **[마키타 18V 배터리 DIY 전원 인출 도크 어댑터 기술 사양서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_power_dock_adapter_technical_spec.md)**
   - 알리익스프레스 구매 정보 및 기구 도면(31/25/39.3mm 마운팅 홀)
   - 14AWG 고내열 리드선 및 전기적 연속/피크 방전 스펙 (18~21V 직결)
   - **필수 안전 수칙**: 15.0V 저전압 차단(LVD) 및 20A 인라인 퓨즈 설계 권장도
   - DIY 응용 어플리케이션(USB-PD 파워뱅크, 12V 전원공급기, Power Wheels 등) 매핑
4. **[마키타 18V 배터리 기반 IoT 센서용 스마트 전원공급 타이머 기술 제안서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_smart_iot_power_timer_proposal.md)**
   - 대용량(100Wh) 배터리 기반 무전원 야외 IoT 시스템 아키텍처
   - **4대 핵심 솔루션**: 초저 대기전력(<15µA), 15.0V LVD, 하이사이드 P-MOSFET 파워 게이팅, 스마트폰 BLE/Web 스케줄링
   - 고효율(95%) 동기식 벅(TPS54302) 다중 전압(3.3V/5V/12V/18V) 출력단 설계
   - PoC 프로토타입부터 PCB 일체형 통합 및 3D 프린팅 하우징 로드맵
5. **[마키타 18V 배터리용 USB & Type-C 충전 어댑터 기술 사양서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_usb_type_c_adapter_technical_spec.md)**
   - 알리익스프레스 구매 정보 및 제품 외형 분석
   - USB-A / Type-C 방전 출력 특성 및 스펙
   - 마키타 배터리 파워뱅크화 및 임베디드 장비 전원 공급 활용 방안
   - 내장 저전압 차단(LVD) 보호 및 엔지니어링 주의점
6. **[프로젝트 작업 이력서](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_work_history.md)**
   - 프로젝트 착수 이후의 모든 작업 이력, 기술 분석 결과, 파일 트리 및 향후 작업 계획 기록
   - 신규 세션 시작 시 최우선 컨텍스트 복원용 문서

---

## 🚀 향후 개발 예정 어플리케이션 후보

- [ ] **고출력 USB-PD 충전기/파워뱅크** (USB-C 65W/100W 양방향 모듈)
- [ ] **12V 차량용 및 캠핑용 전원 공급기** (18V to 12V High-power Buck Converter)
- [ ] **휴대용 고휘도 작업등/캠핑 랜턴** (PWM 디밍 제어)
- [ ] **모바일 로봇 / DC 모터 구동 파워 트레인**
- [ ] **휴대용 220V 소형 인버터 스테이션**
