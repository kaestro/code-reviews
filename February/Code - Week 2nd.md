# Algorithms v3 - Week 2

## https://github.com/kaestro/algorithms_v3/commit/77ec890aefcc049d6cc8f0d8437909e4b6bf72db

1. 특정한 값을 가지고 있는지 확인 할 경우, 해당 값을 hash 형태로 바꾸는 것이 순회하는 것보다 유리하다.
2. python의 set은 hashtable의 형태로 구현돼있다.

## https://github.com/kaestro/algorithms_v3/commit/a9cadb633155bdb7a584575d3ae43b0aeb7121bc
:matrix score

1. 기존 해결방법: brute force
   1. 2-d list를 만들고
   2. 요구하는 대로  list의 element에 대한 반전 연산을 수행한 뒤
   3. list를 binary number로 치환하는 메소드 작성

    * 문제점: 2-d list를 세로로도 순회해야해서 컴퓨터 연산적으로 불리한데, 이를 반복해야한다는 시점에서 O(n^3) 알고리즘이었음
2. 개선 방법
    : 실제로 값을 바꿀 필요가 없다. 순회하면서 바로 결과값을 얻자.


## https://github.com/kaestro/algorithms_v3/commit/ea23a451316766fde8bfce5213a8e9e23781da50
: beauty of sum of all substrings

1. 기존 해결방법: brute force
    * 실제로 substring을 전부 만들고, 이 값에 접근해서 beauty라는 값을 연산한뒤 더하자
    * substring 만드는 것이 O(n^2)알고리즘이고, 이 substring을 읽고 계산하는 과정이 O(n)이므로 O(n^3) 알고리즘
    
2. 개선 방법: substring을 만들지 않고 만들려고 순회하던 시점에 해당 연산을 하는 것이 가능하다. 이 때 beauty라는 값은 직전 substring을 만들 때 계산한 값과 1만 다르기 때문에, 이를 hashmap의 형태로 저장해왔으면 적은 연산만을 사용해서 과정을 이어나갈 수 있다.

## https://github.com/kaestro/algorithms_v3/commit/f3a8270953fd8f49ece53c5f61967753716ce6ad
: merge to form target triplet

특정한 연산만을 사용할 수 있는 상황에서 목표 값을 얻을 수 있는지 확인하는 문제.

최소한의 연산만을 해야하는 것이 아니고, 가능한지 여부만 따져도 될 경우에는 단순하게 해당 연산을 반복해 나가는 것도 문제를 해결하는 좋은 방법이 될 수 있다.

위 문제는 merge를 하면 안되는 값에 적용했을 경우(triplet 중 하나의 값이라도 목표보다 큰 경우)를 제외하면 몇 번을 연산하더라도 결과값에 영향을 미치지 않는다.

그러면 element들을 한 번 순회하는 것만으로 답을 구할 수 있기 때문에, element가 이미 정렬돼있거나 한 것이 아닐 경우 최적의 답이 된다.O(N)