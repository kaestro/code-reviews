# Algorithms v3 - Week 3

## https://github.com/kaestro/algorithms_v3/commit/607e42d6f21d52a45a9354e73ebfc1375393b624

두 집단을 비교해야하는 상황에서, 한쪽 집단의 형태가 일정하게 유지되고 있을 때 이에 대해 loop이 돌고 있다면 이를 줄이는 방법을 찾아보자.

위 문제의 경우는 subset strings를 비교할 때 피비교자인 string 한 번마다 subset strings를 모두 순회하고 있었던 문제가 있었다.

이를 hash를 통해 해결한 방법.

python의 hashmap 같은 경우는 |= 연산을 통해 값을 추가하는 것이 가능하다.

## https://github.com/kaestro/algorithms_v3/commit/e340e9f7148257f6953f98e6c49bb660a777e684

노드를 제거하는 문제이므로 'post-order' 방식으로 순회하는 것이 구현에 용이하다.

## https://github.com/kaestro/algorithms_v3/commit/1b741f135ef9e50422594bf0afad45293fea112c

1. sort를 이용하면 O(nlogn)으로 해결이 가능하다. 이 때, 음수를 두개만 곱하면 양수가 되기 때문에 sort이후 맨 앞의 둘을 곱하고 가장 큰 값을 곱하거나, 최대 셋을 곱하면 된다. python의 경우는 이를 nums[0] * nums[1] * nums[-1], nums[-1] * nums[-2] * nums[-3]으로 해결이 가능하다.

2. 직접적으로 순회하면서 최대값을 찾는 방법도 있다. 위 문제는 전체 값이 필요하지 않고 최대값 3개와, 최소값 2개 + 최대값 1개만 필요하므로 이를 위한 연산을 수행하면 된다.

## https://github.com/kaestro/algorithms_v3/commit/471f6fb0b0c8cba6890b13ca1fbce871dd05eada

list의 element를 순회하면서 일정 구간의 합이 목표값과 같은 경우를 찾고, 이를 제거하는 문제.

1. 목표값 찾는 방법: hash를 통해 element의 accumulative sum에 해당하는 tail node를 저장해둔다. 이러면 그 accumulative sum을 가지는 구간이 존재할 때 가장 마지막 node가 저장된다.
2. 제거하는 방법: 다시 accumulative sum을 순회하면서, hash 상에 해당 값이 이미 존재하는지 확인한다. 존재할 경우 이는 저장된 node와 current node 사이의 합이 0이라는 뜻이므로 currentNode.tail = savedNode.tail.next로 연결을 끊어버리면 된다.
3. 순회하기 위해서는 이후에 currentNode = currentNode.next로 연결을 이어나가면 된다.