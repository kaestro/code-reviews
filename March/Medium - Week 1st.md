1. https://lab.scub.net/architecture-patterns-sharding-09f759150d3d
2. https://medium.com/@dmosyan/handling-partial-failure-in-microservices-applications-2314d3093edb

---

## Architecture Patterns : Sharding
: db의 로드를 분산하기 위한 샤딩의 다양한 방법들에 대한 설명

샤딩은 데이터베이스의 로드를 분산하기 위한 방법으로, 데이터베이스의 크기가 커지면서 데이터베이스의 성능이 저하되는 것을 방지하기 위해 사용된다. 이 글에서는 샤딩의 다양한 방법들에 대해 설명한다.

1. horizontal sharding
2. vertical sharding
3. hash-based sharding
4. range-based sharding
5. directory-based sharding
6. geo-sharding

---

## Handling Partial Failure in Microservices Applications
: 마이크로서비스 애플리케이션에서 부분적인 실패를 처리하는 방법에 대한 설명

1. asynchronous communication
2. retries with exponential backoff
3. network timeouts
4. circuit breakers
5. fallbacks
6. limit number of queued requests