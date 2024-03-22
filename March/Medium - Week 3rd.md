# Weekly Medium Articles - Week 3rd of March

1. <https://kim-dragon.tistory.com/276>
2. <https://levelup.gitconnected.com/mastering-kubernetes-overcoming-complexity-and-accelerating-your-learning-journey-095acb2c8257>
3. <https://medium.com/@joaovitorcoelho10/building-a-performance-testing-tool-from-scratch-03dc7acb3687#cf59>
4. <https://levelup.gitconnected.com/ai-is-discovering-new-antibiotics-a-task-previously-deemed-extremely-challenging-for-humans-7e51b1965d3c>
5. <https://netflixtechblog.com/timestone-netflixs-high-throughput-low-latency-priority-queueing-system-with-built-in-support-1abf249ba95f>
6. <https://medium.com/cwan-engineering/rabbitmq-concepts-and-best-practices-aa3c699d6f08>
7. <https://medium.com/dataprophet/mastering-kafka-cluster-understanding-the-essential-concepts-for-success-b7a2b59236d5>
8. <https://medium.com/@dmosyan/why-do-you-need-api-gateway-770f10e02beb>
9. <https://medium.com/@stewart/we-dont-sell-saddles-here-4c59524d650d>

---

## [Devops] Cilium이란?

iptable을 통해 네트워크를 관리하는 것이 아닌, eBPF를 통해 네트워크를 관리하는 기술인 Cilium에 대한 글. Cilium은 eBPF를 통해 네트워크를 관리하기 때문에 iptable을 통해 관리하는 것보다 더 빠르고, 더 많은 기능을 제공한다. 또한, Cilium은 Kubernetes와도 호환이 잘 되기 때문에 Kubernetes 환경에서 사용하기 좋다.

최근에 kubernetes에 대해 관심을 가지게 되면서 도움이 되는 내용이라 선정

---

## Mastering Kubernetes: Overcoming Complexity and Accelerating Your Learning Journey

kubernetes가 무엇인지에 대해서 개요를 제시하고 이에 대한 자세한 디테일을 포함하는 글. 최근 공부하면서 개념적으로 이해하기 어려운 부분들이 종종 있는데 도움이 될 것 같다.

---

## Building a Performance Testing Tool from Scratch

성능 테스트 도구를 만드는 과정에 대한 글이지만, 주요 내용은 golang이 가지는 특성들에 대한 이유이다. 내가 프로젝트를 사용하는데 golang을 선택한 명백한 근거를 가지고 있지 못했다는 생각이 들어, 이를 점검할 자료를 찾고 있던 중이기에 유용했다.

---

## AI is Discovering New Antibiotics, a Task Previously Deemed Extremely Challenging for Humans

'할리신'과 '아바우신'이라는 새로운 항생제를 인공지능을 통해 발견했다는 글. 인공지능이 이런 실전적인 문제를 해결하는 사례를 보면서, 인공지능이 가지는 가능성에 대해 다시 한번 생각해보게 되었다.

---

## TimeStone: Netflix’s High Throughput, Low Latency Priority Queueing System with Built-in Support for Dynamic Workload Scaling

Netflix에서 사용하는 TimeStone이라는 시스템에 대한 글. 우선순위 큐를 처리하기 위해 시스템을 설계하는 과정의 내용이 흥미롭다.

---

## RabbitMQ Concepts and Best Practices

최근에 채팅 어플리케이션의 메시지 전달을 위한 수단으로 kafka를 사용하려던 계획에서, 다른 기술을 비교할 필요를 느끼게 됐고 그 중 하나가 RabbitMQ이다. 이와 관련한 정보를 찾고 있던 중에 간략한 개요를 알 수 있었고, 이 기술 스택이 비교적 kafka에 비해 가벼워 보인단 인상을 받을 수 있었다. 정확한 비교는 더 해봐야 하겠지만.

---

## Mastering Kafka Cluster: Understanding the Essential Concepts for Success

kafka에 대한 기본적인 개념과 클러스터를 구성하는 방법에 대한 글. 해당 글에서 kafka는 분산처리를 통해 대용량의 스트림을 처리하는 것이 기존의 RabbitMQ와 같은 Message Queue들과 비교해서 장점이라고 강조하고 있다. 이 부분은 이제 내가 분산 처리가 필요한 프로젝트인지에 대한 고려가 선행해야하고, 테스트할 방법을 만들어서 진행하는 필요가 있단걸 알 수 있었다.

---

## Why Do You Need API Gateway?

API 게이트웨이라는 개념을 이 글을 통해 처음 알게 됐다. 추후에 관련해서 찾아볼 의향이 있다.

---

## We Don’t Sell Saddles Here

우리는 '채팅 프로그램'을 파는 것이 아니라 '기술 혁신'을 판다는 이야기를 slack에서는 하고 있다. 이런 마케팅, 그리고 기술의 본질에 대해 요즈음 고민하게 되는 일이 많아 도움이 많이 됐다.