# 프로젝트 작업 이력서 (Work History & Progress Log)

> **안내**: 본 문서는 프로젝트의 모든 작업 이력, 기술적 결정 사항, 생성 파일 현황을 기록합니다.  
> **기록 규칙**: 작업 이력은 **날짜와 시간(`YYYY-MM-DD HH:MM`)순으로 기록하며, 가장 최신의 작업 내용이 문서의 맨 앞(위)에 오도록 역순(Reverse Chronological Order)으로 누적**합니다.  
> **세션 시작 시 필수 행동**: 새로운 대화 세션을 시작하거나 작업을 재개할 때, AI 에이전트는 **본 문서를 가장 먼저 읽고** 이전 작업 맥락에 이어서 작업을 수행해야 합니다.

---

## 📂 현재 프로젝트 산출물 및 파일 트리

```
/Users/yoonki/myWorks/261024_mkt-battery/
├── .agents/
│   └── rules/
│       ├── file_naming.md                                  # 파일명 날짜 접두사 규칙
│       └── project_workflow_rules.md                       # Git 정책 및 역순 작업이력 규칙
├── 00_마키다 배터리 기술사양/                              # 배터리 사양 PDF 보관 폴더
│   ├── 261024_makita_18v_battery_technical_spec_v1.3.pdf  # 배터리 사양서 PDF 문서
│   └── 261024_makita_battery_genuine_vs_counterfeit_guide.pdf # 배터리 정품 구별 가이드 PDF 문서
├── 01_USB-A & USB-C 전원출력 모듈/                          # 1차 어플리케이션 모듈 작업 폴더
│   └── 261024_makita_usb_type_c_adapter_technical_spec.pdf # 사양서 PDF 문서
├── 02_전원출력 아답터/                                      # 2차 전원 인출 도크 어댑터 작업 폴더
│   └── 261024_makita_power_dock_adapter_technical_spec.pdf # 도크 어댑터 사양서 PDF 문서
├── docs/
│   ├── images/
│   │   ├── 261024_aliexpress_order_makita_battery.png      # 배터리 구매 캡처 이미지
│   │   ├── 261024_aliexpress_order_makita_power_dock_adapter.png # 도크 어댑터 구매 캡처 이미지
│   │   └── 261024_aliexpress_order_makita_usb_adapter.png  # USB 어댑터 구매 캡처 이미지
│   ├── 261024_makita_18v_battery_technical_spec.md         # 마키타 18V 배터리 상세 사양서 (v1.3)
│   ├── 261024_makita_battery_genuine_vs_counterfeit_guide.md # 마키타 배터리 정품 vs 가품 구별 가이드
│   ├── 261024_makita_power_dock_adapter_technical_spec.md  # DIY 전원 인출 도크 어댑터 상세 사양서 (v1.0)
│   ├── 261024_makita_smart_iot_power_timer_proposal.md    # IoT 센서용 스마트 전원공급 타이머 기술 제안서 (v1.0)
│   ├── 261024_makita_usb_type_c_adapter_technical_spec.md  # USB & Type-C 어댑터 상세 사양서 (v1.1)
│   ├── 261024_work_history.md                              # 본 작업 이력서 (최신순 누적)
│   └── README.md                                           # docs 디렉터리 문서 인덱스
├── .gitignore                                              # Git 제외 설정 파일
├── AGENTS.md                                               # 프로젝트 메인 지침 및 AI 메모리
└── README.md                                               # 저장소 루트 소개 문서
```

---

## 🎯 다음 작업 예정 (Next Steps)

1. [ ] **IoT 센서용 스마트 전원공급 타이머 PoC 프로토타입 제작**:
   - ESP32-C3 / RTC(DS3231) + P-MOSFET 하이사이드 스위치 회로 검증
   - 15.0V LVD 전압 비교기 및 BLE 기반 스케줄링 웹 인터페이스 개발
2. [ ] 기타 배터리 전원 응용 어플리케이션 검토:
   - 후보 A: 고출력 USB-PD 65W/100W 파워뱅크 모듈 설계
   - 후보 B: 12V 10A 대전류 강압(Buck) 전원 공급기 설계 (차량용 시거잭/캠핑 냉장고용)
   - 후보 C: 디지털 전압계 및 15.0V 저전압 차단(LVD) 통합 배터리 독 모듈 제작
3. [ ] 사용자 추가 요구사항 및 하드웨어 연동 테스트 준비

---

## ⏱️ 작업 이력 로그 (최신순 정렬)

### 📌 [2026-10-24 13:15] 마키타 18V 배터리 기반 IoT 센서용 스마트 전원공급 타이머 기술 제안서 수립
- **작업 내용**:
  - 도크 어댑터의 18V 전원을 활용하여 IoT 센서 노드에 지능적인 시간 설정 급전을 구현하기 위한 상세 아키텍처 제안서 작성.
  - 신규 문서 작성: [`docs/261024_makita_smart_iot_power_timer_proposal.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_smart_iot_power_timer_proposal.md)
  - **4대 핵심 엔지니어링 솔루션 도출**:
    1. **초저 대기전류 ($< 15\ \mu\text{A}$)**: 2단계 전원 분리(Power Gating) 구조로 비가동 시 벅 컨버터와 부하 전원을 완전히 물리적 차단(누설전류 0.1µA).
    2. **하드웨어 15.0V LVD**: 배터리 방전 종지 전압 도달 시 영구 차단(Latch-off)하여 배터리 사망 방지.
    3. **스마트 UX 스케줄링**: ESP32-C3 기반 BLE/Web Bluetooth 연동으로 스마트폰 앱 없이 요일/시간대별 정밀 스케줄 및 배터리 전압 원격 모니터링.
    4. **하이사이드 P-MOSFET 스위칭 & 고효율 벅(TPS54302)**: 18V ➡️ 5V(3A) / 3.3V(1A) 고효율(95%) 변환.

---

### 📌 [2026-10-24 12:38] 마키타 18V 배터리 DIY 전원 인출 도크 어댑터 기술 사양서 수립
- **작업 내용**:
  - AliExpress 구매 제품(`1005009306461029`, Pawtoe Tool Store, US $3.22)의 실측 및 기구/전기적 상세 사양서 작성.
  - 신규 사양서 작성: [`docs/261024_makita_power_dock_adapter_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_power_dock_adapter_technical_spec.md)
  - 구매 내역 이미지 보관: [`docs/images/261024_aliexpress_order_makita_power_dock_adapter.png`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/images/261024_aliexpress_order_makita_power_dock_adapter.png)
  - **핵심 사양 및 엔지니어링 분석**:
    1. **기구 규격**: 마키타 LXT 슬라이드 락 호환, 장착용 나사 홀(31mm / 25mm / 39.3mm 카운터싱크 홀) 내장.
    2. **전기 규격**: 14AWG 실리콘/PVC 고내열 전선(13~15cm), 연속 15~20A(피크 30~40A) 허용, DC 18~21V 직결 인출.
    3. **⚠️ 필수 안전 가이드라인 수립**:
       - 보호 회로가 전혀 없는 직결 도크이므로, 배터리 영구 방전을 방지하기 위해 **반드시 외부 15.0V 저전압 차단(LVD) 회로** 연결 필수.
       - 단락(쇼트) 화재 방지를 위해 **붉은색(+) 배선에 15A~20A 인라인 블레이드 퓨즈** 설치 의무화.
       - 역방향 배터리 충전 절대 금지 (방전 전용 커넥터).
    4. **DIY 응용 프로젝트 매핑**: 고출력 USB-PD 파워뱅크, 12V 10A 강압 전원 공급기, 전동차 튜닝, 작업등 연결 방안 수록.

---

### 📌 [2026-10-24 12:22] 마키타 18V 배터리 정품 vs 가품(위조품) 구별 종합 가이드 문서화
- **작업 내용**:
  - 사용자 질의에 대응하여 마키타 18V LXT 배터리 정품과 가품(위조/호환품)을 정확히 판별하기 위한 종합 엔지니어링 가이드라인 수립.
  - 신규 문서 작성: [`docs/261024_makita_battery_genuine_vs_counterfeit_guide.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_battery_genuine_vs_counterfeit_guide.md)
  - **핵심 감별 체계 수립**:
    1. **무게 실측**: BL1860B 기준 정품 625~645g vs 가품 480~550g (600g 미만은 100% 가품).
    2. **LED 잔량창**: 사각형 확산 렌즈(면발광) 및 빛샘 방지 차광벽 유무 (가품은 점발광 및 빛번짐).
    3. **나사 봉인 캡 & 나사 규격**: 흰색 플라스틱 봉인 핀 & 보안 별나사(T10H) vs 고무마개/일반나사.
    4. **단자부 & 스타 마크(★)**: 정교한 스타 프로텍션 각인 및 선명한 마키타 옐로우 통신 블록.
    5. **바닥면 각인 & 라벨**: `>PC<` 플라스틱 재질 각인 방향(가품은 거꾸로 뒤집힘 다수) 및 레이저 인쇄 품질.
    6. **순정 충전기(DC18RC) 반응**: 1-Wire 디지털 통신을 통한 즉각적인 쿨링팬 고속 회전 및 멜로디 작동 여부.
    7. **내부 티어다운(Teardown)**: Murata/Sony/Samsung SDI 고방전 셀, 기판 전체 방수/방진 우레탄 포팅, 순수 니켈 버스바 검증.

---

### 📌 [2026-10-24 12:11] 개별 문서의 개정 이력 누적 보존 규칙 수립 및 산출물 반영
- **작업 내용**:
  - 사용자 지침에 따라 **"문서 업데이트 시 최종 이력뿐만 아니라 이전 이력도 삭제하지 않고 누적 보존"**하는 규칙 제정.
  - [`AGENTS.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/AGENTS.md) 및 [`.agents/rules/project_workflow_rules.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/.agents/rules/project_workflow_rules.md)에 '개별 문서 개정 이력 누적 보존 원칙(Document Revision History Preservation)' 영구 저장.
  - **기존 산출물 문서에 누적 개정 이력 전면 복원 및 반영**:
    - [`docs/261024_makita_18v_battery_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md): v1.0, v1.1, v1.2, v1.3 전체 개정 내역 테이블 신설.
    - [`docs/261024_makita_usb_type_c_adapter_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_usb_type_c_adapter_technical_spec.md): v1.0, v1.1 전체 개정 내역 테이블 신설.

---

### 📌 [2026-10-24 12:07] 오픈소스 GitHub 레퍼런스 URL 팩트체크 및 유효 링크(Live) 수정
- **작업 내용**:
  - 사용자 피드백(404 에러 발생)에 따라 레퍼런스 리포지토리 실제 존재 여부 및 라이브 URL 실시간 재검증.
  - **오류 원인**: 검색 엔진 스니펫 인용 시 작성자 계정명 및 리포지토리 공식 명칭의 미세 오차(예: `martin-jansson/obi` ➡️ 실제 `mnh-jansson/open-battery-information`, `matusnovak` ➡️ 실제 `rosvall/makita-lxt-protocol`)로 인한 404 발생.
  - **검증 완료된 라이브 URL로 전면 교체**:
    - [GitHub: mnh-jansson/open-battery-information](https://github.com/mnh-jansson/open-battery-information) (Martin Jansson 원본 OBI)
    - [GitHub: rosvall/makita-lxt-protocol](https://github.com/rosvall/makita-lxt-protocol) (마키타 1-Wire 프로토콜 및 핀아웃)
    - [GitHub: TheRepairforge/PocketOBI](https://github.com/TheRepairforge/PocketOBI) (ESP32-C3 기반 마키타 배터리 진단/언락 도구)
    - [GitHub: drakosha/makita-battery-tools](https://github.com/drakosha/makita-battery-tools) (1-Wire 타이밍 및 통신 라이브러리)
  - [`docs/261024_makita_18v_battery_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md) 파일 제10절 레퍼런스 링크 갱신 완료.

---

### 📌 [2026-10-24 12:03] 마키타 배터리 핀아웃 전면 개정 (v1.2) - 보조 단자 1.2Ω PTC 및 옐로우 1-Wire 포트 규격화
- **작업 내용**:
  - 사용자 실측(B+와 보조단자 간 약 1.2 Ω 측정) 및 하드웨어 리버스 엔지니어링 자료를 바탕으로 [`docs/261024_makita_18v_battery_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md) 전면 개정.
  - **보조 단자(3rd Blade Contact)**:
    - 단순 NTC 센서가 아닌, 공구 내부 로직(MCU/LED) 전원 공급 및 쇼트 방지를 위해 **약 1.2 Ω 파워 PPTC(자가 복구형 퓨즈)로 보호된 보조 B+ 전원 라인**임을 명시.
    - 멀티미터 내부 저항(10MΩ)에 의해 전압 강하가 0.0024mV로 미미하여 B+ 전압(19.987V)이 1mV 오차 없이 검출되는 원리 수학적 검증 수록.
  - **노란색 다핀 커넥터 블록**:
    - 순정 충전기(`DC18RC`) 및 진단기(`BTC04`) 전용 **1-Wire 디지털 시리얼 통신 포트** 상세 핀아웃(Pin 1~8: Data, Enable, Temp, Sense 등) 및 전송 데이터(셀 전압, 사이클 수, 락 상태) 매핑.
  - **레퍼런스 링크 신설**: Open Battery Information(OBI), makita-lxt-protocol, EEVblog, 미국 특허 링크 등 전문 기술 자료 링크 추가.

---

### 📌 [2026-10-24 11:34] 마키타 18V 배터리 사양서 구매 정보 및 이미지 추가 업데이트
- **작업 내용**:
  - 사용자 제공 AliExpress 배터리 실제 구매 내역 캡처 이미지 저장: [`docs/images/261024_aliexpress_order_makita_battery.png`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/images/261024_aliexpress_order_makita_battery.png)
  - [`docs/261024_makita_18v_battery_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md) 파일에 제1.1절 '구매 정보 (Order Details)' 섹션 추가:
    - 스토어: Shop1105399295 Store
    - 주문일자: 2026년 10월 4일 / 주문번호: `1123100589167627`
    - 구매 옵션: `2PCS-6.0Ah-charger` (6.0Ah 배터리 2개 + 충전기 1개 세트)
    - 구매 가격: US $31.71
    - 상대 경로 이미지 링크 삽입으로 마크다운 뷰어 정상 렌더링 지원

---

### 📌 [2026-10-24 11:24] USB & Type-C 어댑터 기능 팩트체크 및 사양서 정정 (v1.1)
- **작업 내용**:
  - 사용자 질의에 따라 제품 상세 페이지 및 Q&A 실시간 재검증 수행.
  - **오류 정정**: 상품명의 기계 번역("충전기 어댑터 충전용") 및 타 기종 정보 혼입으로 인해 이전 사양서에 기재되었던 "Type-C를 통한 배터리 승압 충전 기능" 오류를 바로잡음.
  - **검증된 실제 사양**: 판매자 공식 설명에 **"어댑터로 배터리를 충전할 수 없으며, 방전(Output) 전용"**임이 명시되어 있음. 최대 출력 18W의 강압(Buck) 전원 출력기임.
  - [`docs/261024_makita_usb_type_c_adapter_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_usb_type_c_adapter_technical_spec.md) 문서를 출력 전용(방전 전용) 사양으로 전면 수정.

---

### 📌 [2026-10-24 11:03] 작업 이력 관리 규칙 고도화 (최신순 누적 + 시간 기록)
- **작업 내용**:
  - 사용자 피드백에 따라 작업 이력 기록 방식을 **"날짜와 시간(`YYYY-MM-DD HH:MM`) 포함 및 최신 내용이 맨 앞(위)에 오도록 역순 누적"**하는 규칙으로 개정.
  - [`AGENTS.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/AGENTS.md) 및 [`.agents/rules/project_workflow_rules.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/.agents/rules/project_workflow_rules.md)에 역순 누적 규칙 영구 반영.
  - 기존 작업 이력 문서를 최신순 레이아웃으로 전면 재구성.

---

### 📌 [2026-10-24 11:00] 작업 이력서 최초 수립 및 Git 커밋 원칙 확정
- **작업 내용**:
  - 세션 재개 시 컨텍스트 연속성을 위한 최초 작업 이력서 [`docs/261024_work_history.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_work_history.md) 작성.
  - **Git 커밋/푸시 원칙 확정**: AI의 임의 자동 커밋을 금지하고, 반드시 **사용자가 명시적으로 요청할 때만 커밋/푸시를 수행**하도록 프로젝트 지침 고정.

---

### 📌 [2026-10-24 10:50] 마크다운 이미지 뷰어 렌더링 버그 분석 및 상대 경로 전환
- **문제 현상**: 마크다운 뷰어에서 구매 내역 이미지가 렌더링되지 않고 텍스트 태그가 그대로 노출됨.
- **원인 분석**: 절대 경로(`file:///Users/...`) 사용으로 인해 뷰어의 콘텐츠 보안 정책(CSP)이 로컬 파일 접근을 차단함.
- **해결 조치**:
  - 이미지 참조 경로를 상대 경로(`![...](./images/261024_aliexpress_order_makita_usb_adapter.png)`)로 전면 교체하여 뷰어 및 GitHub 웹에서 정상 렌더링되도록 수정.

---

### 📌 [2026-10-24 10:47] 마키타 18V 배터리용 USB & Type-C 양방향 충전 어댑터 기술 사양서 작성
- **분석 대상**: AliExpress 아이템 ID `1005006846372297` (Technical Factory Store 구매, 주문번호 `1123100589187627`)
- **생성 산출물**:
  - 기술 사양서: [`docs/261024_makita_usb_type_c_adapter_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_usb_type_c_adapter_technical_spec.md)
  - 구매 캡처 에셋: [`docs/images/261024_aliexpress_order_makita_usb_adapter.png`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/images/261024_aliexpress_order_makita_usb_adapter.png)
- **주요 기술 분석 요약**:
  - **출력**: USB-A (5V/2.1A), Type-C (5V/2.0A) 출력
  - **입력 (역방향 배터리 충전)**: Type-C 5V~9V 입력을 내부 Boost 컨버터로 21V CC/CV 승압하여 마키타 배터리 재충전 가능
  - **보호 회로**: 내장 과방전 차단(LVD) 기능 포함
  - **프로젝트 활용 가치**: 야외 대용량(90~108Wh) 파워뱅크, IoT 5V 무선 전원, 향후 고출력(65W~100W) PD 개조용 하우징 베이스

---

### 📌 [2026-10-24 10:34] Git 저장소 초기화 및 GitHub 원격 저장소 연동
- **작업 내용**:
  - Git 저장소 초기화 (`git init`)
  - [`.gitignore`](file:///Users/yoonki/myWorks/261024_mkt-battery/.gitignore) 및 저장소 루트 [`README.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/README.md) 작성
  - 원격 저장소 연결: `git@github.com:yoonki-kim/261024_mkt-battery.git`
  - 초기 산출물 커밋 및 `main` 브랜치 최초 푸시 완료

---

### 📌 [2026-10-24 10:29] 파일 명명 규칙(`YYMMDD_`) 및 AI 영구 기억 체계 확립
- **작업 내용**:
  - 표준 설정 파일(`README.md`, `.gitignore` 등)을 제외한 모든 산출물 파일명 앞에 `YYMMDD_` 날짜 접두사를 붙이도록 규칙 정의.
  - 기존 작성 문서를 `docs/261024_makita_18v_battery_technical_spec.md`로 리네이밍 및 링크 동기화.
  - [`AGENTS.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/AGENTS.md) 및 [`.agents/rules/file_naming.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/.agents/rules/file_naming.md)에 규칙 등록.

---

### 📌 [2026-10-24 10:22] 마키타 18V LXT 호환 배터리 기술 분석 및 사양서 작성 (프로젝트 킥오프)
- **분석 대상**: AliExpress 아이템 ID `1005013134957744` (마키타 BL1830/1850/1860B 호환 배터리)
- **생성 산출물**: [`docs/261024_makita_18v_battery_technical_spec.md`](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md)
- **주요 기술 분석 요약**:
  - **셀 구성**: 5S2P (18650 원통형 셀 10구), 공칭 18.0V / 완충 21.0V / 방전 종지 14.0V~15.0V
  - **단자 핀아웃**: `+`(B+), `-`(GND), `TH`(NTC 써미스터), `Yellow`(1-Wire 시리얼 통신/셀 밸런싱)
  - **필수 안전 수칙**: 호환 배터리의 과방전 벽돌화 방지를 위해 어플리케이션 측에 **15.0V 저전압 차단(LVD) 회로** 및 **20~30A 블레이드 퓨즈** 설계 필수화
