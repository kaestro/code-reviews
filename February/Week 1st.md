# Algorithms_v3 - Week 1

## https://github.com/kaestro/algorithms_v3/commit/886b271b3be97d6af2af270d2754ebb8127f4d88

Increasing order search tree. 기존의 bst를 right child로만 연결된 bst로 변환하는 문제. 

* 기존 내 풀이:
  * inorder로 순회하면서 list에 저장한 후, list를 순회하면서 right child로 연결하는 방식으로 풀이
* 개선된 풀이:
  * inorder로 순회하면서 바로 right child로 연결하는 방식으로 풀이
  * 노드에 도착했을 때, inorder 방식이므로 무조건 이번에 순회한 값은 여태까지 생성하고 있는 tree의 가장 오른쪽 노드의 right child에 위치하게 된다.
  * 이 때문에 node를 right child로 연결한 뒤, right child를 다음 current로 설정해 두어 연결할 지점을 계속해서 유지하면서 순회할 수 있다
* 생각해 볼 점:
  * 순회하는 과정 자체가 순서대로라면, 이를 따로 저장할 필요 없이 바로 원하는 결과를 생성하는 것이 좋다.

## https://github.com/kaestro/algorithms_v3/commit/449fc65f0fbc29330042bb3b0153b16b0049a167

string을 element로 갖는 array를 입력받았을 때, 모든 element에 공통으로 들어간 character의 리스트를 구하는 문제. 중복을 허용하여 동일 character가 정답에 2번 이상 등장할 수도 있다.
* ex) ["bella","label","roller"] -> ["e","l","l"]

* 기존 내 풀이:
  * 각각의 string에 대해 character의 count를 센다. 없을 경우에는 0으로 처리한다.
  * 모든 string의 count들의 각각의 character에 대해, 가장 작은 값을 구한다.
  * 이를 바탕으로 정답을 구한다.
* 기존 풀이 개선
  * 파이썬 dictionary의 & 연산은 두 dictionary에 대해 공통으로 존재하는 key-value pair를 반환한다. 이를 이용하여 각 string에 대해 count를 세고, 이를 & 연산을 통해 구할 수 있다.
  * 굳이 확인할 필요 없는 hit하지 않는 캐릭터들에 대한 연산 등 다양한 불필요한 연산을 줄일 수 있어 퍼포먼스가 개선된다.
* best solution:
  * 첫 번째 string을 기준으로 존재하는 character의 set을 생성한다.
  * 각각의 string에 대해 해당 character의 set에 존재하는 character의 횟수 중 minimum 만큼을 정답에 추가한다.
* 생각해 볼 점:
  * 실제로 접근하지 않는 값(이 경우는 string에 존재하지 않는 character)들에 대한 연산이 사용되고 있다면, 이를 어떻게 하면 줄일 수 있을 것인가?
  * python의 built-in function인 dictionary &


## https://github.com/kaestro/algorithms_v3/commit/90c7db2c8ff37d1ddf24b0a187fbe85de7ddd380

세 명의 아이에게 줄 사탕의 갯수와 한 아이에게 줄 수 있는 최대 사탕의 갯수가 주어졌을 때, 이를 나눠 줄 수 있는 경우의 수를 구하는 문제.

* 기존 내 풀이:
  * 3중 for문을 사용하면서, 각각의 사탕을 더할 수 있는 횟수를 0부터 limit까지 더해가면서 경우의 수를 구한다
* 개선된 풀이:
  * 각각의 사탕을 더하는 과정에서 실제로 더하는가 아니면 더한 값을 초기화하는 지를 신경써서 최적화한다.
* best solution:
  * 2중 for문 만을 사용한다.
  * 실제로 더하는 것이 아니라, 목표의 값에서 여태까지 얻은 횟수를 빼내는 형식으로 계산해야하는 횟수를 줄이는 접근이 가능하다.
  * 마지막의 경우는 실제로 모든 경우를 확인할 필요 없이, 남은 사탕의 갯수가 limit보다 작은지만 확인하면 된다.
* 생각해 볼 점:
  * 실제로 더하는 것이 아니라, 빼내는 방식으로 접근할 수 있는 경우가 있는가?
  * 내가 따지고 있는 경우의 수 중에서 실질적으로는 세 보지 않아도 되는 경우가 있는가?