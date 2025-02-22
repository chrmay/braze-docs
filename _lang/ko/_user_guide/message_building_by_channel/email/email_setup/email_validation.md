---
nav_title: 이메일 Validation 
article_title: 이메일 Validation
alias: "/email_validation/"
page_order: 3
page_type: reference
description: "이 참조 문서에서는 이메일 주소의 로컬 및 호스트 부분 유효성 검사 규칙을 다룹니다."
channel: email

---

# 이메일 유효성 검사

> 이 참조 문서에서는 이메일 주소의 로컬 및 호스트 부분 유효성 검사 규칙을 다룹니다.

유효성 검사는 대시보드 이메일 주소, 최종 사용자 이메일 주소(고객), 이메일 메시지의 발신 및 회신 주소에 사용됩니다. 이메일 유효성 검사는 사용자의 이메일 주소가 업데이트되었거나 API, CSV 업로드 또는 소프트웨어 개발 키트를 통해 Braze로 가져오거나 대시보드에서 수정될 때 수행됩니다. 귀하의 이메일 주소에는 공백을 포함할 수 없습니다. API를 사용하는 경우 공백이 `400` 오류를 발생시킵니다.

Braze는 특정 문자를 허용하지 않으며 유효하지 않은 문자로 인식합니다. 이메일이 반송되면 Braze는 이메일을 유효하지 않은 것으로 표시하고 구독 상태는 변경되지 않습니다.  

{% details 허용된 문자 %}
- 문자 (A-Z)
- 숫자 (0-9)
- 기호
	- -
	- ^
	- +
	- $
	- ''
	- &
	- #
	- 에서
	- %
	- *
	- =
	- \`
	- \|
	- ~
	- !
	- ?
	- . (only between letters or other characters)
{% enddetails %}

{% details 허용되지 않는 문자 %}
- 공백 (ASCII 및 유니코드)
{% enddetails %}

이 검증은 Briteverify와 같은 검증 서비스와 혼동하지 마십시오. 이것은 이메일 주소의 구문이 올바른지 확인하기 위한 검사입니다. 이 검증 프로세스를 사용하는 주요 동인 중 하나는 이메일 주소의 로컬 부분에서 국제 문자를 지원하는 것입니다(예: UTF-8).

이메일 구문 검사는 이메일 주소의 로컬 부분과 호스트 부분을 모두 확인합니다. 로컬 부분은 @ 앞의 모든 것이고, 호스트 부분은 @ 뒤의 모든 것입니다. 예를 들어, 이메일 주소의 이 로컬 부분은 마침표(.)를 제외한 허용된 문자로 시작하고 끝날 수 있습니다. 이 프로세스는 이메일 주소의 구문만 유효성 검사하며 도메인에 유효한 MX 서버가 있는지 또는 도메인에 나열된 사용자가 존재하는지 여부는 고려하지 않습니다.

{% alert note %}
도메인 부분에 비-[ASCII](https://en.wikipedia.org/wiki/ASCII) 문자가 포함된 경우 Braze에 제공되기 전에 [Punycode로 인코딩](https://www.punycoder.com/)해야 합니다.
{% endalert %}

Braze가 사용자를 추가하라는 요청을 받고 이메일 주소가 유효하지 않은 것으로 간주되면 API에서 오류 응답을 보게 됩니다. CSV를 통해 업로드할 때 사용자가 생성되지만, 이메일 주소는 추가되지 않습니다.

## 로컬 부분 유효성 검사 규칙

### 일반 이메일 유효성 검사

대부분의 도메인에서는 로컬 부분이 다음 매개변수를 따라야 합니다:
- 모든 문자, 숫자, 유니코드 문자 및 숫자뿐만 아니라 다음 문자도 포함할 수 있습니다: (+) (&) (#) (_) (-) (^) 또는 (/)
- 다음을 포함할 수 있지만 다음 문자로 시작하거나 끝날 수 없습니다: (.)
- 큰따옴표(")를 포함할 수 없습니다
- 1과 64자 사이여야 합니다


다음 정규표현식을 사용하여 이메일 주소가 유효한지 확인할 수 있습니다:
```
/\A([a-zA-Z0-9_\-\^+$'\&#\/!%\*=\?`\|~]|[[^\p{ASCII}\p{Space}]&&\p{Alnum}\p{Punct}\p{S}])(([a-zA-Z0-9_\-\^+$'\&#\/!%\*=\?`\|~\.]|[[^\p{ASCII}\p{Space}]&&\p{Alnum}\p{Punct}\p{S}])*([a-zA-Z0-9_\-\^+$'\&#\/!%\*=\?`\|~]|[[^\p{ASCII}\p{Space}]&&\p{Alnum}\p{Punct}\p{S}]))?\z/
```

{% alert important %}
도메인 부분이 Gmail 주소인 경우 로컬 부분은 최소 두 글자 이상이어야 합니다. 이것은 이 섹션에 나열된 정규표현식 유효성 검사에 추가된 것입니다.
{% endalert %}

### Microsoft 도메인

호스트 도메인에 "msn", "hotmail", "outlook" 또는 "live"가 포함된 경우, 다음 정규표현식을 사용하여 로컬 부분을 검증합니다: `/\A\w[\-\w]*(?:\.[\-\w]+)*\z/i`

Microsoft 주소 로컬 부분은 다음 매개변수를 따라야 합니다:

- 문자(a-z), 밑줄(_), 또는 숫자(0-9)로 시작할 수 있습니다.  
- 영숫자 문자(a-z 또는 0-9)나 밑줄(_)을 포함할 수 있습니다
- 다음 문자들을 포함할 수 있습니다: (.) 또는 (-) 또는 (+) 또는 (^)
- 마침표(.)로 시작할 수 없습니다
- 두 개 이상의 연속된 마침표(.)를 포함할 수 없습니다
- 마침표(.)로 끝날 수 없습니다

로컬 부분이 "+" 앞에 있는 정규표현식과 일치하는지 확인하는 유효성 검사 테스트에 유의하십시오.

## 호스트 부분 유효성 검사 규칙

IPv4 또는 IPv6 주소는 이메일 주소의 호스트 부분에 허용되지 않습니다. 최상위 도메인(예: .com, .org, .net 등)은 완전히 숫자로만 구성될 수 없습니다.

다음 정규표현식은 도메인을 검증하는 데 사용됩니다:<br>
`/^[a-z\d](?:[a-z\d-]{0,61}[a-z\d])?(?:\.[a-z\d](?:[a-z\d-]{0,61}[a-z\d])?)+$/i`

도메인 이름은 다음 매개변수를 따라야 합니다:

- 두 개 이상의 기간으로 구분된 레이블로 구성됩니다
	- 도메인 이름의 각 부분은 "레이블"이라고 합니다. 예를 들어, 도메인 이름 "example.com"은 "example" 레이블과 "com" 레이블로 구성됩니다.
- 적어도 하나의 마침표(.)를 포함해야 합니다
- 두 개 이상의 연속된 마침표를 포함할 수 없습니다
- 각 기간별 레이블은 다음을 충족해야 합니다:
	- 영숫자 문자(a-z 또는 0-9)와 하이픈(-)만 포함
	- 알파벳 문자(a-z) 또는 숫자(0-9)로 시작
	- 알파벳 또는 숫자 문자(a-z 또는 0-9)로 끝납니다
	- 1에서 63자 사이로 포함

### 추가 검증 필요

도메인의 최종 레이블은 최종 마침표(.) 이후의 모든 것으로 결정되는 유효한 최상위 도메인(TLD)이어야 합니다. 이 TLD는 [ICANN의 TLD 목록][2]에 있어야 합니다. Braze 이메일 유효성 검사기는 이 섹션에 나열된 정규표현식에 따라 이메일의 구문이 올바른지 여부만 확인합니다. 오타나 존재하지 않는 주소를 잡아내지 못합니다.

{% alert important %}
유니코드는 이메일 주소의 로컬 부분에만 허용됩니다. 유니코드는 도메인 부분에 허용되지 않지만, 퓨니코드로 인코딩될 수 있습니다.
{% endalert %}

[2]: https://data.iana.org/TLD/tlds-alpha-by-domain.txt
