---
nav_title: AI를 통한 콘텐츠 QA
article_title: AI를 통한 콘텐츠 QA
page_order: 10
description: "이 참조 문서에서는 메시지 작성기에서 직접 AI를 사용하여 메시지 콘텐츠의 품질 보증을 수행하는 방법에 대해 설명합니다."
---

# AI를 통한 콘텐츠 QA

> 메시지 작성자가 직접 AI를 사용하여 메시지 콘텐츠의 품질 보증을 수행하는 방법을 알아보세요.

AI를 사용한 콘텐츠 QA는 GPT 및 OpenAI의 기능을 사용하여 메시지 콘텐츠를 검사하고 맞춤법 오류, 문법 문제, 부적절한 어조, 불쾌한 언어와 같은 비효율적인 요소를 식별하여 품질 표준을 준수하는지 확인합니다. 캠페인 또는 캔버스에서 푸시, SMS 또는 인앱 메시지를 작성할 때 **테스트** 탭에서 이 기능에 액세스할 수 있습니다.

## 주요 기능

AI를 사용한 콘텐츠 QA는 다음과 같은 주요 기능을 제공하여 메시지 콘텐츠의 품질을 향상시킵니다:

- **맞춤법 및 문법 검사:** 메시지의 맞춤법 및 문법 오류를 자동으로 확인합니다. 콘텐츠의 전반적인 정확도를 높이기 위해 수정 사항을 제안하고 권장 사항을 제공합니다.
- **톤 분석:** 메시지의 어조를 평가하여 잠재적인 문제를 식별합니다. 의도한 어조가 원하는 커뮤니케이션 스타일과 일치하도록 하고 오해나 의도치 않은 불쾌감을 피하는 데 도움이 됩니다.
- **모욕적인 언어 감지:** 잠재적으로 모욕적이거나 부적절한 언어가 있는지 메시지를 스캔하여 콘텐츠를 수정하고 정중한 커뮤니케이션을 유지할 수 있습니다.
- **실수로 콘텐츠 확인:** 의도치 않게 추가되었을 수 있는 코드, 마크업 언어 또는 테스트 메시지의 포함 여부를 감지합니다.

## AI로 콘텐츠 QA에 액세스하기

{% alert note %}
현재 AI를 사용한 콘텐츠 QA는 푸시 및 SMS 채널에서만 사용할 수 있습니다.
{% endalert %}

콘텐츠 검사기에 액세스하려면 다음 단계를 따르세요:

1. 푸시 또는 SMS 메시지를 작성한 후 **테스트** 탭으로 이동합니다.
2. **AI를 사용한 콘텐츠 QA** 섹션을 찾습니다.
3. **콘텐츠 테스트를** 클릭합니다.

![테스트 탭의 AI를 사용한 콘텐츠 QA 섹션에서 확인할 수 있습니다.][1]{: style="max-width:60%"}

### 언어 지원

OpenAI는 공식적으로 [여러 언어를](https://openai.com/research/gpt-4#:~:text=GPT%2D4%203%2Dshot%20accuracy%20on%20MMLU%20across%20languages) 지원하지는 않지만 GPT는 [여러 언어를](https://openai.com/research/gpt-4#:~:text=GPT%2D4%203%2Dshot%20accuracy%20on%20MMLU%20across%20languages) 이해할 수 있습니다. Braze는 메시지 콘텐츠가 OpenAI로 전송될 때 사본의 언어 또는 로캘에 대한 추가 정보를 전달하지 않으므로, 해당 결정은 GPT의 몫입니다.

작성하는 언어에 따라 결과가 달라질 수 있습니다.

## 효과적인 사용을 위한 팁

AI를 사용한 콘텐츠 QA 기능을 최대한 활용하려면 다음 팁을 고려하세요:

- **메시지를 교정합니다:** 콘텐츠 검사기는 오류를 식별하는 데 도움이 될 수 있지만 여전히 콘텐츠를 수동으로 교정하는 것이 필수적입니다. AI가 생성한 제안을 유용한 가이드로 활용하되, 정확성을 보장하기 위해 여러분의 판단을 활용하세요.
- **톤 분석을 이해합니다:** 어조 분석 결과는 주관적이며 AI 모델의 이해를 기반으로 합니다. 유용한 인사이트를 제공할 수 있지만, 의도한 어조와 대화 맥락을 고려하여 적절하게 조정하세요.
- **신고된 불쾌감을 주는 언어를 다시 확인하세요:** 모욕적인 언어 감지는 강력하게 설계되었지만 간혹 오탐으로 표시될 수 있습니다. 플래그가 지정된 섹션을 주의 깊게 검토하고 필요에 따라 적절하게 변경하세요.

## 내 데이터는 어떻게 사용되어 OpenAI로 전송되나요?

메시지 내용을 확인하기 위해 Braze는 이를 OpenAI의 API 플랫폼으로 전송합니다. Braze에서 OpenAI로 전송되는 모든 쿼리는 익명으로 처리되므로, 사용자가 제공하는 메시지 콘텐츠에 고유 식별 정보를 포함하지 않는 한 OpenAI는 해당 쿼리가 누구로부터 전송되었는지 확인할 수 없습니다. [OpenAI의 API 플랫폼](https://openai.com/policies/api-data-usage-policies) 약관에 명시된 바와 같이, Braze를 통해 OpenAI의 API로 전송된 데이터는 모델을 학습하거나 개선하는 데 사용되지 않으며 30일 후에 삭제됩니다. [사용 정책](https://openai.com/policies/usage-policies) 및 [공유 및 게시 정책을](https://openai.com/policies/sharing-publication-policy) 포함하여 귀하와 관련된 OpenAI의 정책을 준수해야 합니다. Braze는 AI가 생성한 콘텐츠와 관련하여 어떠한 종류의 보증도 하지 않습니다.

[1]: {% image_buster /assets/img/content_qa_ai.png %}
