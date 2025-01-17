# Weekly Medium Articles - Week 4th of March

1. <https://levelup.gitconnected.com/i-learned-both-rust-go-to-find-out-which-one-was-better-spoiler-alert-its-rust-573e0def4978>
2. <https://blog.ydb.tech/when-postgres-is-not-enough-performance-evaluation-of-postgresql-vs-distributed-dbmss-23bf39db2d31>
3. <https://medium.com/illumination/wittyfeed-a-40-million-company-that-evaporated-overnight-the-reason-facebook-blocked-them-b7b38c750399>
4. <https://medium.com/@ashely.crouch/how-disposable-objects-have-lead-to-disposable-people-7e52096b1b23>
5. <https://medium.com/edge-coders/the-mistakes-i-made-as-a-beginner-programmer-ac8b3e54c312>
6. <https://uxdesign.cc/why-is-the-world-losing-color-56f740f465d4>

---

## rust vs go: 승자는 rust이다

Go가 학습하기 용이하고, 가지고 있는 장점도 있지만 더 안전하고 성능이 좋은 코드를 작성하기에 Rust가 더 적합하다는게 저자의 주장이다.

저자의 주장을 요약하면 다음과 같다

Go | Rust
--- | ---
Go는 쉽게 배울 수 있다 | Rust는 배우는 것이 어렵다
memory safety를 보장하지 않는다 | Rust는 memory safety를 보장한다
클라우드 및 기타 네트워킹 도메인을 위한 확장 가능한 동시 애플리케이션을 쉽게 구축할 수 있다 | 메모리 안전, 성능 및 하위 수준 제어를 목표로 하는 강력한 시스템 프로그래밍 언어를 목표로 한다.

Rust에도 관심을 많이 가지고 있는 만큼, 시간을 내서 한 번 공부해볼 계획을 세워봐야겠다.

---

## Postgres가 충분하지 않을 때: Postgres vs 분산 DBMS 성능 평가 by TPC-C

Postgres는 매우 강력한 오픈 소스 RDBMS이지만 **수직적 확장**만 가능하단 점에서 한계가 있다는 가정에서 시작한 글이다. 그렇다면 **수평적인 확장**이 뛰어난 DBMS는 뭐가 있고, 그 성능은 어떨까?

여기서는 비교 대상으로 **YDB**를 제안하고, 비교하기 위한 성능 테스트로 **TPC-C**를 사용했다. TPC-C는 **OLTP**(OnLine Transaction Processing) 성능을 측정하는 벤치마크 테스트이다. 이에 대한 자세한 내용은 추후에 찾아볼 필요가 있을 것 같다.

결과적으로, 주어진 테스트 환경 내에서 **승자는 PostgreSQL**이었다. PostgreSQL은 분명 약점이 있고 불리한 환경에서도 조금 더 **높은 tpmC**를 보여줬다. 하지만 **New Order Latency**에서는 **YDB**가 큰 차이로 우세했고, **더 큰 수평적 확장**을 구축할 경우에는 tpmC에서도 YDB가 더 높은 성능을 보일 것이라고 예상된다.

최근 다양한 **데이터를 처리**하는 기술과 **분산 처리** 기술에 대해 관심을 가지고 있었는데, 이 글을 통해 더 깊게 공부해볼 수 있는 계기가 되었다.

---

## 빌린 땅 위에 성을 짓지 말라: 하루만에 4천만 달러가 증발한 이유

흔히 **유니콘**이라 불리는 스타트업은 기업 가치가 10억 달러 이상인 10년 이하 비상장 기업을 말합니다. **Witty Feed**는 이에 근접했었던 기업으로, 한 달 만에 **100만 달러의 수익**을 낼 정도로 성장했었습니다. **트래픽은 수백만명**에 달했습니다. 그리고 그 *트래픽은 하루만에 단 몇 천명으로 줄었고 수익은 0으로 떨어졌습니다.*

그 이유는 **페이스북**에서 **캠브릿지 애널리티카**라는 회사가 페이스북 사용자의 개인 데이터를 정치 광고를 위해 무분별하게 침해했다는 이유로 페이스북이 연방거래위원회로부터 **50억 달러의 벌금**을 부과 받은 것에서 시작했습니다. 페이스북은 **트래픽 알고리즘**을 완전히 변경했고 WittyFeed의 플랫폼을 해제했으며 도메인을 차단했습니다.

WittyFeed는 계좌에 돈이 한 푼도 남지 않았고, 직원들은 급여를 받지 못했습니다. 하지만 창립자들은 이 사태에서 미지급 급여의 두 배에 해당하는 회사 지분을 제공하고 마침내 새로운 OTT 플랫폼인 Stage를 구축하는데 성공합니다. 현재 가치는 약 4천만 달러에 달합니다.

이처럼 자신이 소유하지 않은 독점적인 플랫폼에 의존하는 것은 위험하다는 것을 배울 수 있는 글이었습니다. 또한, 이러한 위험을 줄이기 위해 **다양한 플랫폼에 투자**하고 **자체 플랫폼을 구축**하는 것이 중요하다는 것을 배울 수 있었습니다.

---

## 일회용 물건이 일회용 사람을 만들었다

Bic 펜, Temu, Hinge. 이것들의 특징은 무엇일까요? 그것은 이들이 우리에게 한 번 사용하고 버릴 수 있는 편리한 것임을 강조한다는 것입니다. 우리에게 위 제품들은 필요할 때 잠깐 쓰고, 필요 없을 때는 버릴 수 있으면 되니 편하게 사용해보라고 이야기합니다.

그리고 이들을 사용하기 시작하는 순간, 우리는 이들에게서 벗어날 수 없게됩니다.

이처럼 일회용은 본인들이 일회용임을 강조하지만, 일회용의 물품이 아니란 것을 글에서 주장합니다. 그리고 이것들이 가져다주는 사회적인 폐단으로 여러가지가 있으며, Hinge와 같이 사람의 **관계**에 영향을 주는 단계까지 침범하고 있다고 주장합니다.

그리고 마침내 사람을 **일회용**으로 만들고 있다고 말입니다.

사회적으로 인기를 끌고 있는 많은 제품들이 편리함을 내세울 때, 과연 그것은 우리가 편리한 삶을 살 수 있게 해주는 것인지 아니면 이들에 종속되는 일회용 삶을 살게 하는 것인가에 대한 의문을 가지게 하는 글이었습니다.

---

## 초보 프로그래머로서 저지른 실수들

저자가 초보시절 겪었던 실수들을, 후배들은 이러한 실수를 하지 않기 위해 경험을 공유하고자 작성한 글입니다. 총 25가지의 실수를 나열하고 있으며, 그 중 인상깊었던 것들은 다음의 것들이 있습니다.

* Always write the minimum amount of code that you need today for the solution that you are implementing. Handle edge-cases, sure, but do not add edge-features.
  * 최근에 계획을 너무 크게 세웠다가 시작 지점을 찾지 못하고 이것저것 학습만 하다가, MVP를 먼저 만들어야한다는 결론에 도달한 적이 있습니다.
* Writing without Planning & Planning Too much Before Writing Code
  * 이 때문에 계획을 세우는 것은 중요하지만, 무엇보다 계획을 어떻게 세우는지에 대한 명확한 기준이 있어야한다는 생각을 하게 됐습니다.
  * 또한 계획을 적당히 세우는 것에 대해서도 생각해보게 됐습니다.
* What we tend to overlook as beginners is that there is an alternative to using recursive functions. You can just use a Stack structure. Push function calls to a Stack yourself and start popping them out when you are ready to traverse the calls back.
  * 재귀함수를 작성할 일이 잦지는 않지만, 이에 대해 주의할 필요가 있단 걸 다시 한 번 느꼈습니다.
  * 재귀함수는 아무래도 성능에서나, 디버깅에서나 많은 면에서 불리할 수 있기 때문입니다.
* Premature optimization is the root of all evil (or at least most of it) in programming
  * Donald Knuth의 유명한 말입니다. 알고리즘 문제를 풀다보면 최적화에 대해 완성 전부터 고민하게 되는 경우가 종종 있는데, 주의하려합니다.
* Reinventing the Wheel
  * 학습의 측면에서 어느 정도는 이전에 구현된 것들을 만들어보는 노력을 하는 것도 좋지만, 일단은 다른 사람은 어떻게 했는지부터 찾아보는 것이 좋다는 조언을 받기도 했고 이에 따라 내 코드를 작성하기 전에 다른 사람의 것을 먼저 참고해봐야겠다는 생각도 어느 정도 들었습니다.

---

## 세상이 색을 잃는 이유

과거와 비교해서 디자인 적인 측면에서 사람들이 더 단조로운 색을 선호하는 경향성이 드러나고 있다는 글. 실제로도 주변에서 보는 전자기기들은 보통 흰색, 회색, 검은색이 주로 선호된다는 생각을 하게 됐다.

이는 사람들이 이전보다 더 색을 통해 개인을 드러내기 보단 무난해 보이려고 하는 경향이 드러나고 있다는 증거가 아닌가? 전반적으로 남들과 비슷해 지려는 경향인가 하는 생각이 든다.

---
