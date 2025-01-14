# Algorithms_v3 - Week 1st

## [Can Make Palindrome from Substring](https://leetcode.com/problems/can-make-palindrome-from-substring/description/)

### Must Review, 금주의 문제

inputs[left:right+1]를 rearrange하고 k번 이하의 문자를 변경해서 palindrome을 만들 수 있는지 확인하는 문제이다.

dp, prefix sum을 통한 (i, j) 구간의 저장 공간 줄이기, xor 연산의 사용, binary로 변환하는 방법 등을 통해 풀이를 개선할 수 있다. [참고자료](https://leetcode.com/problems/can-make-palindrome-from-substring/solutions/371999/python-100-runtime-and-memory/)

내 풀이 개선 과정

1. [prototype without rearrange](https://github.com/kaestro/algorithms_v3/commit/4e0178afb27014628516dc2a47c0c557b9969d19)
2. [saving everything is too much](https://github.com/kaestro/algorithms_v3/commit/3e5f988d9bf8e79222c52e4d2f4bb22d6034436c)
3. [using prefix sum to reduce space](https://github.com/kaestro/algorithms_v3/commit/78b0945d61b74012b3f331c2829354404e73424e)
4. [Use List instead of Dictionary When index range is small and limited. If only odd/even matters don't add and %= 2, use xor](https://github.com/kaestro/algorithms_v3/commit/f8bd0f94ea3eee84ddf7df8df5130967efc02ea5)
5. [If only odd/even number matters, you may change integer into binary]

---

## [가능한 적게 저장하라](https://github.com/kaestro/algorithms_v3/commit/6208041d46052adfabceeb6c1b34685d68896482)

대각선의 값들이 모두 동일한 value를 가지는 지 확인하는 문제이다. 최초의 풀이는 대각선의 값들을 dictionary 안에 저장하고, 이들을 같은지 확인하는 방식으로 구현했다. key로는 (row, col)을 쓰고, mat[(row, col)] == mat[(row-1, col-1)]인지 확인했다.

그런데 이는 최초의 첫 row/col만 확인하면 되는 문제이기 때문에, dictionary에 해당 값들만 저장하고 이를 비교하도록 구현을 변경했다.

이 밖에 key로 row - col을 사용하는 것도 한가지 방법이며, 이 방법을 사용할 경우 dictionary가 아니라 조금의 튜닝을 통해 일반적인 list로도 구현이 가능하다.

---

## [integer 보다 string이 더 빠른 경우. input에 적절한 보정을 사용하는 방법](https://github.com/kaestro/algorithms_v3/commit/825c371389d1f69d10666d23fc8f38bbf650c2b3)

각 수의 자릿수를 가지고 split number를 만든 뒤에 이 중 합이 가장 작은 split sum을 구하는 문제이다.

내 기존 풀이는 integer를 나누고, 나머지를 digits list에 저장하는 방식이었다. 그런데 이러는 것보다 string으로 변환한 뒤 처리하는 것이 더 유리할 수 있다. 이는 각각을 나누는 연산을 진행하는 것보다 string으로 변환하는 것이 빠르기 때문으로 추측된다.

```python
def save_digits_as_int(num: int):
    digits = []
    while num > 0:
        digits.append(num % 10)
        num //= 10
    return digits
```

```python
def save_digits_as_char(num: int):
    return list(str(num))
```

해당 문제는 맨 앞에 0이 나오는 경우를 허용하는 문제이기 때문에 input integer의 자리수가 홀수일 경우 0을 추가해주는 보정을 하면 해결이 쉬워진다.

---

## [pattern을 찾는 문제를, pattern을 만드는 문제로 바꾸어 생각하라](https://github.com/kaestro/algorithms_v3/commit/c0515d3bf3ab61a79de9f97679ffe965902ea9bb)

주어진 integer에 대해 pattern이 [1, 0, -1] 세 가지로 주어지고, 이것들이 부분 순열에서의 증가, 동일, 감소 패턴을 나타내는 문제이다. 그리고 이 pattern이 몇 번 나오는지 확인하는 문제이다.

기존의 내 문제 풀이는 모든 index에 대해 pattern이 존재하는지 확인하는 방식으로 구현했다.

```python
for i in range(len(nums) - len(patterns)):
    for j in range(len(patterns)):
        if patterns[j] == 1 and nums[i + j + 1] <= nums[i + j]:
            break
        elif patterns[j] == 0 and nums[i + j + 1] != nums[i + j]:
            break
        elif patterns[j] == -1 and nums[i + j + 1] >= nums[i + j]:
            break
    else:
        result += 1
```

이 문제는 pattern을 만드는 문제로 바꾸어 생각해서 해결할 수 있다.

```python
def apply_pattern(nums: List[int], pattern: List[int]) -> List[int]:
    ans = []
    for i in range(1, len(nums)):
        if (nums[i] == nums[i - 1]):
            ans.append(0)
        elif (nums[i] > nums[i - 1]):
            ans.append(1)
        else:
            ans.append(-1)
    return ans
```

둘의 시간복잡도는 동일하지만 두 번째 방법이 더 직관적이고 이해하기도 쉬우면서, 더 적은 비교 연산을 수행하기 때문에 성능이 좋게 나타나는 것을 확인할 수 있었다.

---

## [가능한 적게 저장하라 - 2](https://github.com/kaestro/algorithms_v3/commit/f38f736837c54887b8a31bbb59a0806a8b7f2c7b)

기존의 내 풀이는 stream에서 return할 값들을 새로운 list에 저장하고, 이를 return하는 방식으로 구현했다.

```python
result = []
for i in range(self.idx, len(self.stream)):
    if self.stream[i] is None:
        break
    result.append(self.stream[i])
    self.idx += 1
return result
```

그러나 이는 정직한 부분 리스트를 반환하는 함수이기 때문에 새로운 list를 생성할 필요가 없다.

```python
begin = self.idx
while self.stream[self.idx]:
    self.idx += 1

return self.stream[begin:self.idx]
```

---
