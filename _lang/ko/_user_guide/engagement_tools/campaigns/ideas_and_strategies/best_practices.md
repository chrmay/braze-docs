---
nav_title: 모범 사례
article_title: 캠페인 Best Practices
page_order: 0
description: "이 기사는 캠페인을 만들고 사용자 정의하는 모범 사례를 제공합니다."
tool: Campaign

---

# 캠페인 모범 사례

## Braze의 네 가지 T

Braze는 Braze 플랫폼에서 활용할 의도가 있는 고객 데이터만 전송할 것을 권장합니다. "Braze의 Four T's" 철학을 고려하여 사용할 데이터만 전송하도록 하십시오:

- **타겟** 오디언스를 구축하여 [오디언스 세그먼트]({{site.baseurl}}/user_guide/engagement_tools/segments/)를 만드세요.
- **트리거** your messages with [action-based]({{site.baseurl}}/user_guide/engagement_tools/campaigns/building_campaigns/delivery_types/triggered_delivery#action-based-delivery) or [API-트리거된]({{site.baseurl}}/user_guide/engagement_tools/campaigns/building_campaigns/delivery_types/api_triggered_delivery/) 전달.
- **템플릿** and personalize your messages with [Liquid 조건 로직]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/liquid).
- **추적** the efficacy of your campaigns with [전환 추적]({{site.baseurl}}/user_guide/engagement_tools/campaigns/building_campaigns/conversion_events?redirected=true#conversion-events).

이렇게 하면 Braze에 보내는 데이터를 최적화하고 사용자가 추적하지 않는 데이터 포인트를 장기적으로 유용하지 않다고 생각할 수 있는 경우에도 메시지를 보낼 수 있는 기능을 간소화할 수 있습니다. 

## 사용자 타겟팅

시간이 지남에 따라 캠페인을 구축하면서 오디언스에 간격이 생길 수 있습니다. 이 중요한 시점에서 세분화를 사용하여 [이탈 사용자]({{site.baseurl}}/user_guide/engagement_tools/campaigns/ideas_and_strategies/capturing_lapsing_users/)를 대상으로 한 특화된 캠페인을 진행할 수 있습니다. 

### 귀하의 오디언스를 식별하십시오

세그먼트와 필터를 활용하여 오디언스를 정의함으로써 이점을 얻으세요. 귀하의 캠페인과 메시지가 타겟팅하는 대상을 고려하십시오. 이 중요한 정보를 통해 [멀티채널 캠페인]({{site.baseurl}}/user_guide/engagement_tools/campaigns/faq/#how-do-you-create-a-multichannel-campaign)을 생성하여 오디언스의 알림 선호도에 맞게 다양한 채널에서 메시지를 작성할 수 있는 유연성을 제공합니다.

또한 [활성 사용자]({{site.baseurl}}/user_guide/engagement_tools/campaigns/ideas_and_strategies/active_user_campaigns/)를 이해하여 일관된 사용자에게 감사를 표하는 것이 중요합니다.

## 멀티채널 캠페인

### 기능 awareness

사용자를 새로운 기능이나 앱 버전으로 끌어들이는 것이 목표라면, 인앱 채널에 중점을 둔 멀티채널 전략을 사용하세요. 인앱 메시지][5]와 콘텐츠 카드][7]는 사용자가 즉시 업데이트를 원하지 않을 경우에도 일반적으로 덜 방해가 됩니다. 적절한 앱 스토어에 [딥 링크]({{site.baseurl}}/user_guide/personalization_and_dynamic_content/deep_linking_to_in-app_content/)를 포함해야 합니다.

사용자에게 앱을 업데이트하거나 앱 사용 방식을 변경하도록 설득하는 것은 어려울 수 있으므로, 새로운 버전이나 기능의 모든 이점과 앱 사용 경험이 어떻게 향상될 것인지 알려주세요. 

### 보내기 타이밍

타이밍이 중요합니다! 사용자에게 앱 업데이트를 권유하는 것이 목표라면, 앱 내에서 긍정적인 경험을 한 후에 사용자에게 요청하십시오. 오디언스를 계속 참여시키려면, 침입적으로 보일 수 있는 반복적인 메시징을 피하세요.

시간이 지남에 따라 사용자는 특정 기능을 잊어버리거나 새로운 기능을 알아차리지 못할 수 있습니다. 새로운 기능이 추가되면 [앱 내 메시지]({{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/about/)로 사용자에게 알리십시오. 사용자가 앱 내 주요 기능에 참여하지 않는 경우, 앱을 사용할 때 이 새로운 기능이 유용할 것임을 상기시키는 것이 좋습니다. \[데이터 옵트인][7]에 관한 저희 기사에는 사용자의 워크플로우 기대에 부합하는지 확인하는 방법에 대한 더 많은 정보가 있습니다. 

## 높은 평가

모든 모바일 마케터의 위시리스트에는 앱 스토어에서 별 다섯 개의 평가를 받는 것이 포함되어 있습니다. 긍정적인 리뷰를 얻는 것은 쉬운 일이 아닙니다. 왜냐하면 사용자에게 추가적인 노력이 필요하기 때문입니다. 우리의 기능을 현명하게 적용함으로써 고객 참여를 증가시키는 데 도움을 드릴 수 있습니다.

### 타겟팅 파워 유저

고급 사용자는 귀하의 앱을 옹호할 수 있습니다. 종종 그들은 귀하의 앱과 지속적으로 상호 작용하며 귀하의 앱을 개선하기 위한 피드백을 제공할 수 있습니다. 비록 앱마다 다르지만, 파워 유저들은 다음과 같은 경향이 있습니다:

- 많은 세션을 기록했습니다
- 최근에 앱을 사용했습니다
- 돈을 쓰고 구매를 했습니다

더 높은 평가를 받으려면 파워 유저에게 앱 스토어에서 앱을 리뷰하도록 요청하세요. 그들은 좋은 말을 할 가능성이 더 높습니다. 예를 들어, 다음 필터를 사용하여 "Power users"라는 세그먼트를 만들 수 있습니다:
- 지난 14일 동안 이 앱들을 10번 이상 사용했습니다
- 50달러 이상 지출했습니다

![][6]

사용자가 앱 스토어를 방문하는 데 시간이 걸립니다. 그들이 추가적인 노력을 기울일 가능성을 극대화하려면, 앱에서 긍정적인 경험을 한 후에 평가나 리뷰를 요청하세요. 예를 들어, 그들이 게임 레벨을 클리어하거나 할인 코드를 사용하여 구매를 한 후에 물어보세요. 사용자의 워크플로우 기대에 부합하는지 확인하는 방법에 대한 자세한 내용은 [데이터 옵트인]({{site.baseurl}}/user_guide/message_building_by_channel/email/managing_user_subscriptions/#subscription-states)에 관한 저희 기사를 참조하십시오.


[6]: {% image_buster /assets/img_archive/ratings_power_users.png %}
[5]: {{site.baseurl}}/user_guide/message_building_by_channel/in-app_messages/about/
[7]: {{site.baseurl}}/user_guide/message_building_by_channel/content_cards/about/