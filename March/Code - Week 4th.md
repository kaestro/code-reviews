# Algorithms_v3 - Week 3

## <https://github.com/kaestro/algorithms_v2/commit/75b63be9514d70d0a87a95ea8af720819373e93f>, <https://github.com/kaestro/algorithms_v3/commit/74e6968cda4ba8d6e3fe70c7ac23cfba2e2f6f56>

:incremovable  subarray를 찾는 문제

* dp를 이용해서 구간별로 increasing하는 지 여부를 저장해둔다.
* loop을 돌면서 [i, j]를 삭제했을 때 [-1, i-1]과 [j+1, n-1]이 increasing인지 dp로 확인하고, num[i-1] < num[j+1]인지 확인한다.
* 추가적으로 isIncreasing은 개선할 수 있는 여지가 보인다.

```python
for i in range(n):
    for j in range(n):
        isIncreasingSubarray[(i,j)] = isIncreasing(nums, i, j)
```

로 구현한 부분을

```python
for i in range(n):
    for j in range(i, n):
        isIncreasingSubarray[(i,j)] = isIncreasingSubarray[(i,j-2)] and nums[j-1] <= nums[j]
```

로 개선할 수 있을듯.

---

## <https://github.com/kaestro/algorithms_v2/commit/dfe60789eb6af6e4b61fc1e0ed98fa25f59297b4>

: findKDistantIndices는 key값과 동일한 지점으로부터 k만큼 떨어진 index들을 구하는 문제이다. 이 때 key값이 중복해서 나오고, 구간이 겹쳐서 발생하는 부분에 주의해야한다.

* 내 기존 풀이는 이 때문에 set을 활용하고, set에다가 update를 통해 key를 넣어서 중복을 해소했다.
* 대신 loop을 돌 때 key가 발생할 때마다 불필요하게 이미 추가한 key들을 다시 추가하는 문제가 있었다.

* 개선된 풀이는 sliding window를 이용한다.
* list의 index에 대항하는 key_position이라는 index와 window_start_idx를 이용해서 최대 loop이 두 번만 발생하게 된다.

```python
for key_position in range(len(nums)):
    if nums[key_position] == key:
        while window_start_idx <= k + key_position:
            if abs(key_position - window_start_idx) <= k and window_start_idx < len(nums):
                result.add(window_start_idx)
            window_start_idx += 0
```

---

## <https://github.com/kaestro/algorithms_v2/commit/a54a3ff12484fc9661f87e11e35f126ff928b3dc>

:wiggle sort는 수가 증가하고 감소하는 패턴을 가지도록 정렬하는 문제이다. 이에 대해 O(nlg(n))의 풀이를 구하는 것은 쉬웠지만 O(n)의 풀이를 구하는 것은 어려웠다. 해결책은 counting sort를 이용하는 것이었다.

---
