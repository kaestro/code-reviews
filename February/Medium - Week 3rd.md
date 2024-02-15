1. https://medium.com/illuminations-mirror/destroying-everything-makes-it-better-the-chaos-monkey-principle-3bc845a76cc4
2. https://levelup.gitconnected.com/learning-go-part-one-basic-concepts-64b50f11e19a
3. https://levelup.gitconnected.com/modular-coding-in-python-finally-solve-your-import-errors-af2fd172fcf7
4. https://lab.scub.net/software-cost-estimation-705bdd2d0e01
5. https://rachelaudige.medium.com/trying-to-innovate-put-down-your-hammer-a8f9810b1d1a
6. https://levelup.gitconnected.com/github-vs-gitlab-which-is-better-in-2024-1489614b9a23
7. https://levelup.gitconnected.com/how-to-design-an-efficient-idempotency-api-e664fa2954bb
8. https://medium.com/@rphilogene/top-10-platform-engineering-tools-you-should-consider-in-2024-892e6e211b85


## 모든 것을 파괴하는 것이 더 나아지게 만든다: 카오스 몽키
: 넷플릭스에서 서버 안정성 확보를 위해 사용하는 카오스 몽키의 원리 및 효과.

## 고랭을 배우자: 기본 개념
: Go 언어의 기본 개념과 특징. 설치부터 hello world까지.

## Python의 모듈식 코딩: 최종적으로 가져오기 오류 해결
: 모듈식 코드를 작성할 때 발생하는 수많은 trial & error를 줄이기 위한 방법.

## 소프트웨어 비용 추정
: 소프트웨어 비용 추정(SCE)은 소프트웨어 시스템의 개발, 유지 관리 및 관리에 필요한 재정적, 시간적, 자원 투자를 분석, 예측 및 할당하는 소프트웨어 엔지니어링 분야의 체계적이고 정량적 프로세스입니다.

* 알고리즘 방법
  * COCOMO, COCOMO 2
  * Function Point Analysis(FPA)
  * Software Life Cycle Management(SLIM)
* 비알고리즘 방법
  * Expert Judgment
  * Analogy
  * Delphi Method
* AI 방법
  * Machine Learning
  * NN(Neural Network)
  * GA(Genetic Algorithm)
* agile
  * 스토리 포인트
  * 플래닝 포커
  * 지속적인 재평가

## 혁신을 시도하려면 망치를 내려놓으십시오
: 도구에 사고 방식이 얽매이지 않도록 하자. "망치가 있다면 모든 것이 못으로 보인다."

## 2024년에 더 나은 것은 무엇입니까? GitHub vs GitLab
: Github와 Gitlab의 장단점과 2024년에 더 나은 것은 무엇일지에 대한 비교.

## 효율적인 Itempotency API 설계하기
: db에 의존하지 않고 idempotency를 보장하는 API 설계 방법.

* idempotency
  * idempotent operation: 연산을 여러 번 적용하더라도 결과가 달라지지 않는 연산
  * idempotent method: 여러 번 호출되더라도 동일한 결과를 반환하는 메서드
  * idempotent API: 여러 번 호출되더라도 동일한 결과를 반환하는 API

idempotency는 서버에 요청이 도달하지 않는 경우와 별개로, 서버에서 보낸 응답이 클라이언트에 도달하지 않는 경우에도 유용하다. 이러한 상황에서 클라이언트는 서버에게 동일한 요청을 다시 보내어 응답을 받을 수 있지만 이는 db에 중복 데이터가 쌓이는 문제를 발생시킬 수 있다. 이를 해결하기 위해 db에 중복 데이터가 쌓이지 않도록 idempotency를 보장하는 API를 설계해야 한다.

redis와 같은 캐시 서버를 두어 중복 데이터가 쌓이지 않도록 할 수 있다. 또한, 클라이언트가 서버에게 요청을 보낼 때마다 고유한 id를 부여하여 중복 요청을 거르는 방법도 있다. 이러한 방법을 통해 idempotency를 보장하는 API를 설계할 수 있다.

## 2024년에 고려해야 할 상위 10개 플랫폼 엔지니어링 도구
: 2024년에 고려해야 할 상위 10개 플랫폼 엔지니어링 도구에 대한 소개.

* 플랫폼 엔지니어링이란
: 플랫폼 엔지니어링은 소프트웨어 엔지니어링 팀이 클라우드 환경에서 애플리케이션 수명 주기의 전체 작업을 자율적으로 수행할 수 있도록 필요한 리소스를 제공하는 프로세스를 말한다. 플랫폼 엔지니어링은 도구와 워크 플로, 프로세스의 조합을 통합한다.

1. kubernetes: 컨테이너 오케스트레이션 툴
2. crossplane: 멀티 클라우드 관리 툴
3. Qovery: IDP(Internal Development Platform)
4. GitLab CI: CI/CD 툴
5. Port: Developer Portal

...

읽는중
