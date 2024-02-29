1. https://levelup.gitconnected.com/system-design-interview-question-design-spotify-4a8a79697dda
2. https://medium.com/@danielbuilescu/5-python-coding-errors-that-are-killing-your-speed-and-how-to-fix-them-today-8064f4d32e20
3. https://medium.com/@mayilb77/design-a-real-time-leaderboard-system-for-millions-of-users-08b96b4b64ce
4. https://medium.com/@limsungmook/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8%EB%8A%94-%EC%99%9C-%ED%94%84%EB%A1%9C%ED%86%A0%ED%83%80%EC%9E%85%EC%9D%84-%EC%84%A0%ED%83%9D%ED%96%88%EC%9D%84%EA%B9%8C-997f985adb42
5. https://medium.com/@ignacio.de.gregorio.noblejas/google-has-finally-dethroned-chatgpt-87a8f8c10d92
6. https://medium.com/thedeephub/rust-a-new-titan-in-data-science-d449463078b2

---

## Design Spotify
:시스템 디자인 인터뷰 질문: 디자인 Spotify

점점 규모가 큰 시스템을 디자인하게 될 때 어떻게 해야하는지 시스템 디자인 적인 답을 제시한다. cdn, cache 서버, lru, sql 등을 어떤식으로 선택할지에 대한 생각해 볼만한 글

---

## 5 Python Coding Errors That Are Killing Your Speed and How to Fix Them Today
:당신의 속도를 늦추는 5가지 파이썬 코딩 에러와 오늘 고칠 수 있는 방법

1. 기본 루프를 사용하기보다 numpy와 같은 강력한 라이브러리를 사용하라.
2. 자료구조를 적절히 선택하라
3. **cProfile**을 사용하여 코드를 프로파일링하라.
4. 내장함수를 사용하라.
5. 하드 드라이브에서 데이터를 끌고 올때 읽고 쓰는 횟수를 줄여라

---

## Design a Real-Time Leaderboard System for Millions of Users
: 수백만명의 사용자를 위한 실시간 리더보드 시스템 디자인하기

수백만명 단위의 사용자를 위한 리더보드 시스템을 디자인할 때, 수치상으로 목표로하는 결과를 얻으려면 rdbms, redis sorted set, kafka 등의 시스템을 통해 어떻게 해야하는지에 대한 생각을 제시한다.

---

## 자바스크립트는 왜 프로토타입을 선택했을까?
: 클래스가 아니라 프로토타입을 선택한 철학적인 논의

저자는 클래스는 플라톤의 이데아적인 관점에서 객체를 정의하는 것이라면, 프로토타입은 비튜겐슈타인의 전형적인 예시를 통해 객체를 정의하는 것이라고 설명한다. 객체를 분류할 때 공통된 것이 있다고 생각하느냐, 대표적인 것과 유사하느냐에 따라 분류하느냐로 생각하느냐는 기준을 통해 우리는 개발을 할 때 방향을 정할 수 있다는 것이다.

이처럼 개발 과정에서 해결책으로 여러가지 중 하나를 선택할 때, 왜 그것을 선택하는지에 대해 충분하게 고민하는 방법에 대해서 생각해보게 되는 글이다.

---

## Google has finally dethroned ChatGPT
: Gemini 1.5가 MLLM을 통해 세대간 도약으로 ChatGPT를 앞서는 성과를 내는 데 성공했다는 기사

Gemini 1.5에 대해서 사실 사용해 본 적이 없고, 크게 기대하지 않고 있었던 상태였다. 이번 기사를 통해 Gemini 1.5가 기술적으로 ChatGPT를 앞서는 부분들이 상당하단 것을 알게 돼 한 번 사용해 볼까하는 생각이 들었다.

사용해보고 괜찮다면 이를 통한 code generator 기능이 나오는 것을 기대해본다.

---

## Rust: A New Titan in Data Science
: Rust가 데이터 사이언스 관점에서 어떻게 장점을 가지는지에 대한 분석 글

최근에 Rust가 각광받고 있는 인상을 받는다. 에러도 적게 나고, 속도도 빠르고, 동시성도 구현하기에 유리하다. 그렇다 하더라도 구체적으로 이번 처럼 다른 언어(python)과의 비교를 통해 장단점을 분석하는 글을 보게 돼 이해가 더 잘 됐고, 더 관심을 가지게 됐다.