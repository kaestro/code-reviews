1. https://medium.com/@dareobasanjo/5-things-i-learned-about-leadership-from-the-death-rebirth-of-microsoft-3eaf42567061
2. https://medium.com/towards-data-science/how-i-won-singapores-gpt-4-prompt-engineering-competition-34c195a93d41
3. https://medium.com/educative/taylor-swift-ticketmaster-meltdown-a-system-design-analysis-cd326f7ed57b
4. https://medium.com/dev-publicity/advice-to-my-younger-self-and-you-after-20-years-in-programming-a3a2ccc7a942
5. https://levelup.gitconnected.com/modular-coding-in-python-finally-solve-your-import-errors-af2fd172fcf7


## 마이크로소프트의 죽음과 재탄생을 통해 내가 리더십에 대해 배운 5가지

* 현재 가장 혁신적인 기업 중 하나인 마이크로소프트는 어떻게 지금의 모습을 갖게 되었는가

## 싱가포르의 GPT-4 프롬프트 엔지니어링 대회에서 우승한 방법
: LLM(대형 언어 모델)의 기능을 활용하기 위해 배운 전략에 대한 심층 분석

* CO-STAR
  * Context
  * Objective
  * Style
  * Target
  * Audience
  * Response
* 구분 기호 사용을 통한 섹션 나누기
  * ###, ===, >>>
  * XML 태그 사용
* 시스템 프롬프트 사용방법
  * 질문에 답하려면 [텍스트 삽입]이라는 텍스트를 사용하세요
  * {"Question": "Answer"} 형식의 JSON 개체로 응합하시오.
  * 본인이 질문에 답하기에 충분한 정보가 포함되어 있지 않은 경우 정보를 구성하지 말고 "NA"로 답하십시오.


## Taylor Swift Ticketmaster Meltdown: 시스템 설계 분석
: 수십억의 요청이 들어올 때, 이를 유연하게 대응할 수 있는 서버 시스템 설버

* 3가지 방법
  * 캐싱
  * 우아한 저하(Graceful Degradation)
  * 대기실을 없애고, 구매 시간 제한을 설정한다.
* 제 3자 의존성
* 시스템은 가장 약한 링크만큼 강력하다.

## Advice to my younger self and you after 20 years in programming
: 20년간의 프로그래밍 경험을 토대로, 젊은 개발자들에게 조언

일반적으로 많이 하는 조언과 동시에, 하지 않는 조언들도 있다. 인상 깊었던 부분들은 다음 정도.

* 이익을 창출하는 것을 생각하라
* 초기 기술에 참가하고, 죽어가는 기술에서 벗어나라
  * https://survey.stackoverflow.co/2023/#section-salary-salary-and-experience-by-language
* 응용보다 과학을 선택하라. 과학자 1인당 필요한 점점 더 적은 프로그래머가 필요하다.
* IT 업계에서 선두 기업에서 근무하는 것은 차이가 크다.
* '중요한' 오픈 소스에 기여하라
* 미친듯이 공개하라.

## Python의 모듈식 코딩: 최종적으로 가져오기 오류 해결

이번에 파이썬으로 게시판 api 서버를 개발할 때 가장 최초로 난관을 겪었던, 모듈 import. 아직 읽는 중