---
nav_title: 청구서
article_title: 청구서
alias: /subscription_and_usage/
page_order: 25
page_type: reference
description: "이 참조 문서에서는 청구 페이지를 다루며, 여기에서 데이터 소비를 모니터링하고 확인할 수 있습니다."
tool: Dashboard
search_rank: 5
---

# 청구서

> 이 페이지를 셀프 서비스 도구로 사용하여 데이터 소비를 모니터링하고 확인하세요.

**청구** 페이지로 이동하려면 **설정** > **청구**로 이동하십시오.

{% alert note %}
[이전 탐색]({{site.baseurl}}/navigation)을 사용하는 경우 계정 아이콘을 선택한 다음 **구독 및 사용**을 선택하여 이 페이지를 찾을 수 있습니다.
{% endalert %}

**청구** 페이지에는 다음 탭이 포함됩니다:

- [구독 및 사용량](#subscriptions-and-usage)
- [최다 사용 이벤트 and Attributes by 앱](#most-used-events-and-attributes-by-app)
- [총 데이터 포인트 사용량](#total-data-points-dashboard)

## 구독 및 사용량

**구독 및 사용** 탭에는 사용 그래프와 계약 세부 정보가 포함되어 있습니다.

### 사용량 그래프

여기에서 작업 공간에 적용되는 사용 그래프를 찾을 수 있습니다. 구매한 제품에 따라 대시보드에 표시되는 사용 측정기준이 다를 수 있습니다.

![월간 고유 방문자 수를 보여주는 사용량 그래프][3]{: style="max-width:90%;"}

이 그래프는 월간 활성 사용자, 월간 고유 방문자 및 이메일 전송을 보여줄 수 있습니다. 이와 같은 사용 그래프는 사용량을 예산하고 작업 공간이 전체 사용량에 기여하는 바를 더 깊이 이해하려고 할 때 특히 유용합니다.

### 연락처 세부 정보

계약 세부 사항에는 Braze와의 현재 계약 시작일과 종료일이 나와 있습니다.

## 최다 사용 이벤트 및 속성별 앱

**최다 사용 이벤트 및 속성별 앱** 탭은 속성 및 커스텀 이벤트 데이터 포인트 소비의 원인을 이해하는 데 유용한 도구입니다. 앱마다 선택한 기간 동안 특정 커스텀 속성, 프로필 속성 및 커스텀 이벤트의 예상 수와 해당 앱의 속성 및 이벤트 업데이트 중 해당 속성 또는 이벤트에 의해 발생한 비율을 찾을 수 있습니다. 

데이터 분석은 특정 데이터 포인트가 할당량의 큰 비율을 차지하는지 이해하는 데 도움이 될 수 있습니다. 이 정보를 수시로 모니터링하여 데이터 포인트를 실수로 불필요하게 사용하지 않도록 하는 것이 좋습니다. 귀하의 고객 성공 매니저는 현재 계획을 최대한 활용하거나 더 큰 유연성을 위한 옵션을 제공하는 데 도움을 줄 수 있습니다. 

![최다 사용 이벤트 and Attributes By 앱][4]

## 총 데이터 포인트 대시보드

**총 데이터 포인트 사용량** 탭은 데이터 포인트 소비에 대한 심층적인 분석을 제공합니다. 이 섹션에서 모든 데이터를 주 또는 월별로 집계하여 볼 수 있습니다. 클릭 **업데이트** 하여 변경 사항을 적용하십시오.

![주별 데이터 포인트 사용량 필터링][2]

### 연락처 세부 정보

여기에서 현재 Braze 계약이 시작되고 종료되는 시기, 할당된 데이터 포인트 및 현재 계약에서 지금까지 사용된 모든 데이터 포인트의 합계에 대한 정보를 찾을 수 있습니다.

이 섹션의 필드는 다음과 같이 정의됩니다:

- **계약 유형:** 청구 기간 구조, 연간 또는 다년간.
- **계약 시작 및 종료 날짜:** 전체 계약의 시작 및 종료 날짜.
- **할당된 데이터 포인트:** 청구 기간당 계약에 할당된 데이터 포인트의 양.
- **계약 데이터 포인트 사용량:** 계약 기간 동안 소비된 모든 데이터 포인트의 누적 합계이며, 다음 청구 기간에 초기화되지 않습니다.

![계약 세부 정보 섹션의 총 데이터 포인트 사용량 탭][5]

### 현재 청구 주기

대시보드의 이 섹션은 현재 청구 주기의 데이터 포인트 사용량을 표시합니다. 이것은 현재 청구 주기에 대한 다음 정보를 포함합니다:

- 시작일 
- 종료일  
- 할당된 데이터 포인트 수 
- 총 데이터 포인트 사용량 

![현재 청구 주기 섹션의 총 데이터 포인트 사용량 탭][6]{: style="max-width:90%;"}

### 회사 청구 데이터

#### 작업 공간 간의 사용

이 그래프를 통해 작업 공간별로 회사의 총 데이터 포인트 사용량을 평가할 수 있습니다. 이 그래프는 각 작업 공간이 회사의 데이터 포인트 사용량에 어떻게 기여하고 있는지 평가할 수 있는 기능을 제공합니다.

![워크스페이스 데이터 포인트 사용량 그래프 두 개의 워크스페이스][7]{: style="max-width:90%;"}

#### 시간 경과에 따른 데이터 포인트 사용량

이 그래프는 할당된 데이터 포인트 양에 비해 총 데이터 포인트 사용량을 빠르게 확인할 수 있는 기능을 제공합니다. 

![데이터 포인트 사용량 over time contrasting current billing cycle allotted 데이터 포인트 with running total][8]{: style="max-width:90%;"}

### 워크스페이스 청구 데이터

{% alert note %}
워크스페이스 청구 데이터 및 워크스페이스 차트는 2021년 10월 1일 이후의 날짜에만 표시됩니다.
{% endalert %}

#### 작업 공간으로 드릴

**워크스페이스로 드릴 다운** 기능을 사용하면 각 워크스페이스에 대한 세부 데이터 포인트 데이터를 볼 수 있습니다. 워크스페이스를 클릭하여 데이터 포인트 세부 정보를 확인하세요.

![작업 공간으로 드릴 다운하여 청구 가능한 데이터 포인트][9]{: style="max-width:90%;"}

##### 카테고리별 워크스페이스 수준 데이터 포인트 사용량

워크스페이스 이름 옆의 메뉴를 선택한 다음 **WORKSPACE_NAME에 대한 청구 가능 데이터 포인트**를 선택하여 **카테고리별 워크스페이스 수준 데이터 포인트 사용량** 표를 확인합니다. 이 표는 각 데이터 포인트 범주의 데이터 포인트 수를 보여줍니다. 예를 들어, 세션 및 커스텀 이벤트에 의해 구동되는 데이터 포인트 수를 볼 수 있습니다. 이 표를 사용하여 작업 공간의 데이터 포인트 소비를 유도하는 데이터 포인트의 범주를 식별할 수 있습니다.

![워크스페이스 레벨 데이터 포인트 사용량별 카테고리][10]{: style="max-width:90%;"}

##### 시간 경과에 따른 워크스페이스 수준 데이터 포인트 사용량

**시간에 따른 워크스페이스 수준 데이터 포인트 사용량** 테이블은 해당 워크스페이스의 데이터 포인트 사용량이 청구 주기 동안 어떻게 변경되었는지 보여줍니다.

![워크스페이스 레벨 데이터 포인트 사용량 시간 경과][11]{: style="max-width:90%;"}

##### Appl 수준 총 데이터 포인트 사용량

**앱 레벨 총 데이터 포인트 사용량** 테이블은 작업 공간의 각 앱에 대한 데이터 포인트 사용량을 보여줍니다. 이 표를 사용하여 작업 공간에서 데이터 포인트 소비를 유발하는 앱을 식별할 수 있습니다.

![앱 레벨 총 데이터 포인트 사용량 테이블 여러 앱에 대한][12]{: style="max-width:90%;"}


[2]: {% image_buster /assets/img/subscription_and_billing2.png %}
[3]: {% image_buster /assets/img/subscription_and_billing4.png %}
[4]: {% image_buster /assets/img/most_used_events_attributes_time.png %}
[5]: {% image_buster /assets/img/contract_details.png %}
[6]: {% image_buster /assets/img/current_billing_cycle.png %}
[7]: {% image_buster /assets/img/appgroup_datapoint_usage.png %}
[8]: {% image_buster /assets/img/company_data_point_usage_time.png %}
[9]: {% image_buster /assets/img/appgroup_drilldown.png %}
[10]: {% image_buster /assets/img/appgroup_level_datapoint_usage_bycategory.png %}
[11]: {% image_buster /assets/img/appgroup_level_usage_time.png %}
[12]: {% image_buster /assets/img/app_level_stats.png %}