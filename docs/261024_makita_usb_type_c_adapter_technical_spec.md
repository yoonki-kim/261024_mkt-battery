# 마키타 18V 배터리용 USB & Type-C 전원 출력 어댑터 기술 사양서
(Makita 18V Battery to USB & Type-C Power Source Output Adapter Technical Specification)

## 1. 구매 정보 및 제품 개요 (Order & Product Overview)

본 문서는 마키타(Makita) 18V LXT 호환 배터리를 다목적 휴대용 파워뱅크로 변환하여 스마트폰 및 소형 전자기기에 전원을 공급하기 위해 구매한 **USB & Type-C 전원 출력 어댑터 홀더**의 정확한 기술 사양, 내부 동작 특성 및 프로젝트 응용 가이드라인을 정의합니다.

### 1.1 구매 정보

![AliExpress 구매 내역](./images/261024_aliexpress_order_makita_usb_adapter.png)

- **제품명**: 마키타 18V용 USB 및 타입-C 배터리 홀더 (Makita 18V Battery USB & Type-C Power Source Adapter)
- **구매처 링크**: [AliExpress 상품 페이지 (Item ID: 1005006846372297)](https://ko.aliexpress.com/item/1005006846372297.html?spm=a2g0o.order_list.order_list_main.29.4803140fX5nOCd&tblci=GiCS9h0KKgkDTGY9im3LGsf1GfiWaDaM2M480C6x2QXXZiCnqXUorOThsf72yMPqATCCong&gatewayAdapt=glo2kor)
- **스토어**: Technical Factory Store (AliExpress Choice)
- **주문일자**: 2026년 10월 4일
- **주문번호**: `1123100589187627`
- **구매 가격**: US $4.64 (무료 반품 및 배송 보장 옵션)
- **색상 옵션**: Blue (마키타 시그니처 틸 블루 컬러)

---

## 2. ⚠️ 핵심 팩트체크: 배터리 충전 기능 여부 (Important Fact-Check)

> [!CAUTION]
> ### 🚨 판매자 공식 명시 사항 (배터리 재충전 불가)
> 판매자 상세 페이지의 **[개요]** 및 **[Q&A]**에 다음과 같이 공식 명시되어 있습니다:
> 
> 1. **"어댑터로 배터리를 충전할 수 없습니다. 배터리에 충분한 전력이 있으면 연결한 후 USB 및 Type-C 인터페이스를 통해 다른 장치에 전원을 공급할 수 있습니다."**
> 2. **"이 제품은 방전용으로만 사용 가능하며, 배터리 충전 기능은 작동하지 않습니다."**
> 
> ➡️ **결론**: 본 제품은 **오직 마키타 배터리의 전력을 외부로 출력하는 방전 전용(Output Only) 어댑터**입니다.  
> 상품명의 "충전기 어댑터 충전용"이라는 문구는 "스마트폰을 충전하기 위한 어댑터(For Charging Devices)"의 번역 오류이며, **마키타 18V 배터리를 Type-C로 재충전하는 승압(Boost) 회로는 내장되어 있지 않습니다.**

---

## 3. 제품 외형 및 인터페이스 구조 (Hardware & Interface)

```
        ┌───────────────────────────────────┐
        │  [ Makita 18V Slide-on Mount ]    │ (하단: 배터리 슬라이드 체결 레일)
        ├───────────────────────────────────┤
        │                                   │
        │  [Power Button]   [LED Indicator] │ (상단 조작부: 원터치 전원 버튼 & 상태 LED)
        │                                   │
        │   ┌───────────┐   ┌───────────┐   │
        │   │  USB-A    │   │  Type-C   │   │ (전면: 2개 출력 포트 - Output Only)
        │   │ (Output)  │   │ (Output)  │   │
        │   └───────────┘   └───────────┘   │
        └───────────────────────────────────┘
        │          [ Metal Belt Clip ]      │ (후면: 휴대용 메탈 벨트 클립)
```

- **슬라이드 체결부**: 마키타 18V LXT 규격 배터리 상단 홈에 완전히 결합되는 정밀 가이드 레일
- **출력 포트 구성**:
  - **USB-A 포트**: DC 5V 출력 (스마트폰, 태블릿, 소형 기기 충전)
  - **Type-C 포트**: **출력 전용(Output Only)** (스마트폰 고속 충전 지원)
- **조작 버튼**: 원터치 푸시 버튼 (출력 활성화 및 미사용 시 암전류 차단)
- **상태 표시등**: 작동 상태 표시 LED
- **후면 기구**: 스테인리스 스틸 벨트 클립 (작업 벨트, 배낭 스트랩 장착용)

---

## 4. 전기적 및 기계적 상세 사양 (Technical Specifications)

| 항목 (Parameter) | 상세 사양 (Specification) | 비고 (Remarks) |
| :--- | :--- | :--- |
| **기능 분류** | **강압(Buck) 방식 휴대용 전원 출력기** | **방전 전용 (배터리 충전 불가)** |
| **호환 배터리 제품군** | 마키타 14.4V ~ 18V LXT 슬라이드 배터리 | BL1815, BL1830, BL1840, BL1850, BL1860B 등 |
| **배터리 입력 전압 (입력)** | DC 14.0V ~ 21.0V (배터리 직결 수신) | 5S 리튬이온 팩 전압 |
| **최대 총 출력 전력** | **최대 18 W (Max Total Output)** | 전체 포트 합산 한계치 |
| **USB-A 출력** | DC 5V / 2.1A (기본 고속 충전) | 스마트폰, 소형 IT 기기 |
| **Type-C 출력** | DC 5V / 2A ~ 3A (최대 18W 프로토콜) | C-Type 스마트폰 고속 충전 |
| **배터리 충전(입력) 지원** | **❌ 지원하지 않음 (Input 불가)** | Type-C는 출력(Output) 단자로만 동작 |
| **내부 전력 변환 회로** | 강압형 벅 컨버터 (Step-down Buck Converter) | 18V ➡️ 5V/9V 변환 |
| **보호 기능 (Protection)** | 저전압 차단(과방전 방지), 과전류, 출력 단락 보호 | 배터리 전압 저하 시 출력 차단 |
| **하우징 재질** | 내충격성 난연 ABS + PC 엔지니어링 플라스틱 | 견고한 내구성 |
| **외형 치수** | 약 110mm x 70mm x 38mm | 콤팩트한 휴대용 규격 |
| **제품 중량** | 약 110g (배터리 제외) | 초경량 설계 |

---

## 5. 실무 활용 방안 및 엔지니어링 주의사항

### 5.1 실무 활용 방안 (Application Use Cases)
1. **대용량 야외 파워뱅크 (Power Bank)**:
   - 5.0Ah(90Wh) 또는 6.0Ah(108Wh) 마키타 배터리를 결합하여 스마트폰(약 4,000mAh)을 4~5회 이상 충전할 수 있는 비상용 고용량 보조배터리로 활용.
2. **5V 임베디드 장비 무선 전원**:
   - 아두이노(Arduino), ESP32, 라즈베리파이 등 5V 전원을 요구하는 개발 보드를 야외나 전원 콘센트가 없는 작업 현장에서 안정적으로 구동.
3. **작업 현장 및 아웃도어 유틸리티**:
   - 벨트 클립을 활용하여 현장 작업 벨트에 착용, 스마트폰 또는 USB 충전식 작업등/헤드랜턴에 전원 공급.

### 5.2 엔지니어링 주의사항
> [!WARNING]
> 1. **배터리 충전 불가**: 본 어댑터를 꽂은 상태에서 Type-C 케이블로 스마트폰 충전기에 연결해도 **마키타 배터리는 충전되지 않습니다.** 마키타 배터리는 반드시 마키타 전용 충전기(`DC18RC` 등)를 통해 충전해야 합니다.
> 2. **최대 출력 18W 한계**: USB-PD 65W/100W를 요구하는 고출력 노트북(맥북, 그램 등)은 충전할 수 없습니다 (스마트폰/태블릿 충전 전용).
> 3. **iPhone 15/16 케이블 주의**: 판매자 상세 설명에 따르면 일부 최신 C to C 케이블과의 프로토콜 핸드셰이크 호환성 이슈가 있을 수 있으므로 표준 A to C 또는 기본 케이블 사용을 권장합니다.

---

## 6. 관련 자료 및 레퍼런스 링크 (References)

- **제품 구매 페이지**: [AliExpress Item 1005006846372297](https://ko.aliexpress.com/item/1005006846372297.html)
- **마키타 순정 어댑터(ADP05)**: [Makita Official ADP05 USB Power Source Adapter](https://www.makitatools.com/products/details/ADP05)
- **연계 기술 문서**: [마키타 18V 배터리 기술 사양서 (261024_makita_18v_battery_technical_spec.md)](file:///Users/yoonki/myWorks/261024_mkt-battery/docs/261024_makita_18v_battery_technical_spec.md)

---

## 7. 문서 개정 이력 (Revision History)

| 버전 (Version) | 개정 일시 (Date/Time) | 주요 개정 내용 및 변경 사유 |
| :---: | :---: | :--- |
| **v1.1** | 2026-10-24 11:24 | • 사용자 질의에 따라 판매자 상세 설명 및 Q&A 실시간 팩트체크 수행<br>• 기계 번역 왜곡으로 인한 "Type-C 배터리 승압 충전 가능" 오류 정정 ➡️ **"출력 전용(방전 전용, 최대 18W), 배터리 충전 불가"**로 전면 수정<br>• 내부 회로를 승압 회로가 아닌 18V ➡️ 5V/9V 강압(Buck) 컨버터로 정정 |
| **v1.0** | 2026-10-24 10:47 | • 마키타 18V 배터리용 USB & Type-C 어댑터 기술 사양서 최초 작성<br>• AliExpress 실제 구매 캡처 이미지(`docs/images/261024_aliexpress_order_makita_usb_adapter.png`) 및 구매 옵션 반영 |

