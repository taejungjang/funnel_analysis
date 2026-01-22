# [cite_start]이커머스 로그데이터를 통한 퍼널 분석 [cite: 1]

[cite_start]본 프로젝트는 **Google Merchandise Store**의 로그데이터를 활용하여 사용자의 구매 여정을 단계별로 분석하고, 이탈이 발생하는 지점을 진단하여 전환율 개선을 위한 액션 플랜을 도출한 분석 프로젝트입니다[cite: 12, 13, 14].

---

## 1. 분석 배경 및 목적
* [cite_start]**현황**: 온라인 매장에서는 구매까지 여러 복잡한 과정이 존재합니다[cite: 4].
* [cite_start]**문제점**: 단순히 구매율만 확인하면 중간 과정을 놓치게 되어 세분화된 진단이 필요합니다[cite: 5, 6].
* [cite_start]**목적**: 단계별 전환율 파악을 통해 특정 부분의 UX 개선 등 구체적인 해결책을 제시하고자 합니다[cite: 7, 8, 10].

---

## 2. 데이터 개요
* [cite_start]**데이터 명**: ga4_obfuscated_sample_ecommerce [cite: 12]
* [cite_start]**시간적 범위**: 2020/11/01 – 2021/01/31 (3개월) [cite: 15]
* **주요 컬럼**:
    * [cite_start]`event_name`: 구매 과정 시 발생하는 이벤트 (session_start, purchase 등) [cite: 17]
    * [cite_start]`user_pseudo_id`: 각 사용자의 고유값 [cite: 18]

---

## 3. 퍼널 정의 및 전처리
### [cite_start]구매 퍼널 단계 [cite: 36]
1. [cite_start]**Page View**: 웹사이트 방문 [cite: 37]
2. [cite_start]**View Item**: 아이템 확인 [cite: 38]
3. [cite_start]**Add to Cart**: 장바구니 담기 [cite: 39]
4. [cite_start]**Checkout**: 결제 시작 [cite: 40]
5. [cite_start]**Add Payment Info**: 결제 정보 입력 [cite: 41]
6. [cite_start]**Purchase**: 최종 구매 완료 [cite: 42]

### 데이터 전처리 프로세스
* [cite_start]날짜별로 생성된 개별 테이블을 하나로 병합하였습니다[cite: 44, 45].
* [cite_start]사용자(`user_pseudo_id`)를 기준으로 구매 단계를 집계하였습니다[cite: 46].
* [cite_start]필수 단계 기록이 누락된 경우, 이전 단계에 추가하여 데이터 정합성을 보정하였습니다[cite: 47, 48].

---

## 4. 분석 결과



### [cite_start]단계별 전환율 현황 [cite: 50]
| 분석 단계 | 전환율 |
| :--- | :---: |
| 페이지 보기 → 아이템 조회 | [cite_start]**22.7%** [cite: 51, 52] |
| 아이템 조회 → 장바구니 담기 | [cite_start]27.0% [cite: 53, 54] |
| 장바구니 담기 → 주소 입력 | [cite_start]58.5% [cite: 55, 56] |
| 주소 입력 → 결제정보 입력 | [cite_start]59.1% [cite: 57, 58] |
| 결제정보 입력 → 결제 | [cite_start]76.8% [cite: 59, 60] |
| **페이지 보기 → 결제 (전체)** | [cite_start]**1.6%** [cite: 61, 62] |

### 주요 인사이트
* [cite_start]**업계 대비 낮은 전환율**: 패션 업계 평균 전환율(약 2.3%) 대비 본 사이트는 1.6%로 다소 낮습니다[cite: 64].
* [cite_start]**심각한 병목 지점**: 일반적인 상품 페이지 도달률인 50%에 비해 본 서비스는 **22.7%**로 현저히 낮아 구조적 개선이 필요합니다[cite: 66, 67].

---

## 5. 가설 검정: 유입 경로별 도달률 차이
* [cite_start]**가설**: 유입 경로에 따라 상품 조회 도달률에 통계적 차이가 있을 것이다[cite: 72, 73].
* [cite_start]**검정 결과**: 카이제곱 검정 결과, p-value가 0.0000으로 유입 경로별 차이는 유의미합니다[cite: 100, 105].
    * [cite_start]**Referral**: 24.8% [cite: 91, 94]
    * [cite_start]**Organic**: 22.0% [cite: 87, 90]
    * [cite_start]**cpc (유료광고)**: 20.0% [cite: 95, 98]
* [cite_start]**결론**: 모든 경로에서 업계 평균에 미달하며, 특히 cpc의 상품 전환 효율이 가장 낮습니다[cite: 106, 111].

---

## [cite_start]6. 액션 플랜 (Action Plan) [cite: 107]
1. [cite_start]**랜딩 페이지 최적화**: cpc 광고 클릭 시 메인 페이지가 아닌 **'상품 상세 페이지'**로 바로 연결하여 이탈을 방지합니다[cite: 108, 111].
2. [cite_start]**추천 시스템 강화**: 연관 상품 배치를 통해 사이트 체류 시간을 늘리고 대안을 제시합니다[cite: 112, 113, 114].
3. [cite_start]**제품 경쟁력 재고**: 도달률이 매우 낮으므로 **'상품 자체의 시장성(PMF)'**을 재점검하고 근본적인 혁신을 도모합니다[cite: 116, 117, 118, 119].

---
[cite_start]**분석자**: 장태중 [cite: 2]
