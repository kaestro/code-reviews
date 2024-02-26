1. https://levelup.gitconnected.com/system-design-interview-question-design-spotify-4a8a79697dda
2. https://medium.com/@danielbuilescu/5-python-coding-errors-that-are-killing-your-speed-and-how-to-fix-them-today-8064f4d32e20
3. https://medium.com/@mayilb77/design-a-real-time-leaderboard-system-for-millions-of-users-08b96b4b64ce

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