---
nav_title: 위치 타겟팅
article_title: 위치 타겟팅
page_order: 6.5
page_type: tutorial
tool: 
- Segments
- Location
description: "이 도움말 문서에서는 위치 타겟팅을 설정하는 방법을 안내하여 위치별로 사용자를 세분화할 수 있도록 합니다."

---

# 위치 타겟팅

> 이 문서에서는 위치 타겟팅을 설정하는 방법을 안내하여 가장 최근 위치를 기준으로 사용자를 세분화할 수 있도록 합니다. 위치 기반 캠페인 및 전략을 검토하는 경우에 적합합니다.

## 1단계: 세그먼트 만들기

**대상** 아래의 **세그먼트** 페이지로 이동하여 현재 모든 사용자 세그먼트를 확인합니다. 이 페이지에서 새 세그먼트를 만들고 이름을 지정할 수 있습니다. 시작하려면 **세그먼트 생성을** 클릭하고 세그먼트의 이름을 지정합니다.

{% alert note %}
[이전 탐색을]({{site.baseurl}}/navigation) 사용하는 경우 **세그먼트는** **참여** 아래에 있습니다.
{% endalert %}

![][1]{: style="max-width:70%;"}

## 2단계: 위치 사용자 지정

세그먼트를 생성한 후에는 **가장 최근 위치** 필터를 추가하여 사용자가 마지막으로 앱을 사용한 장소를 기준으로 사용자를 타겟팅합니다. 표준 원형 영역 또는 사용자 지정 가능한 다각형 영역에서 사용자를 강조 표시하는 옵션이 있습니다.

![][2]

### 원형 영역

원형 영역의 경우 원점을 이동하고 세분화의 위치 반경을 조정할 수 있습니다.

![뉴저지와 뉴욕 사이의 도시를 원형으로 표시한 윤곽선입니다.][3]{: style="max-width:70%;"}

### 다각형 영역

다각형 영역의 경우 세그먼트에 포함할 영역을 보다 구체적으로 지정할 수 있습니다.

![선택한 다각형 지역으로서 뉴욕주의 윤곽선입니다.][4]{: style="max-width:70%;"}

{% alert tip %}
Braze 파트너의 도움을 받아 위치 타겟팅을 활용하고 싶으신가요? 사용 가능한 Braze [컨텍스트 기반 위치 파트너를]({{site.baseurl}}/partners/message_personalization/location/) 확인하세요.
{% endalert %}

[1]: {% image_buster /assets/img_archive/createsegment2.png %}
[2]: {% image_buster /assets/img_archive/filter_recent_location.png %}
[3]: {% image_buster /assets/img_archive/location_circle.png %}
[4]: {% image_buster /assets/img_archive/create_polygon.png %}
