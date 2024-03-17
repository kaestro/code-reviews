# Algorithms_v3 - Week 3

## <https://github.com/kaestro/algorithms_v3/commit/7d93d121779a27751af49a9a08049bca445ab94b>, <https://github.com/kaestro/algorithms_v3/commit/f069a2ca6bce193757dddf76242b836b6af60d4a>

:beautiful subset을 구하는 두 가지 방법 1. backtracking, 2. 수학적인 연산

* backtracking을 이용한 방법은 모든 경우의 수를 탐색하며, 조건에 맞는 경우만을 선택한다.
* 수학적인 연산은 dp라고 했지만, 실제로 dp를 사용하고 있지는 않다. 과정은 다음과 같다.
  * 현재 수가 beautiful하지 않게하는 값이 num_count에 존재하는지 확인한다.
  * 존재할 경우, 해당 수의 경우의 수를 구한다.
    * 이 때 경우의 수라 함은 해당 값이 subset에 존재하는 경우와, 존재하지 않는 경우를 나누어서 구하게 된다.
  * num_not_included_pair_count는 엄밀하게는 num이 아니라 partner_not_included_pair_count가 더 좋은 표현이다. 이는 num이 beautiful하지 못하게 하는 partner가 있는지 여부를 확인하는 것이기 때문이다. => refactoring needed
  * 기존에 내 풀이 방식은 abs(num - target_diff)가 num_count에 존재하는지 확인하는 방식이었는데, 해당 솔루션은 nums - diff의 존재 여부를 계속해서 확인하므로 어차피 무조건 잡히게 돼있다.
  * 특정 값이 존재하는 subset의 갯수는 그 element의 갯수가 n일 때 2^n - 1이다.
  * 이를 다 감안하면 calculate_dp를 이해할 수 있다.
  * 그런 뒤에 이 값들의 합을 다 곱한 것이 답이 된다.

```python
def calculate_dp(num):
    if (num - diff) not in num_counts:
        partner_not_included_pair_count, partner_included_pair_count = calculate_dp(num - diff)
    else:
        partner_not_included_pair_count, partner_included_pair_count = 1, 0
    return partner_not_included_pair_count + partner_included_pair_count, partner_not_included_pair_count * (pow(2, num_counts[num - diff]) - 1)
```

---

## <https://github.com/kaestro/algorithms_v3/commit/eda23a1d47ad46abd5cdb6042a37e41b97a9b13c>

* 기존 내 솔루션은 alpha가 아닌 것의 위치를 고정한 뒤, alpha인 것들을 순서대로 다시 집어넣어서 loop을 두번 돌아야 했다.
* 개선한 솔루션은 alpha가 아닌 것이 나올 때는 좌우의 pointer를 움직이고, 둘 다 alpha일 경우 스왑하여 loop을 한 번만 돌면 된다.

```python
def reverseOnlyLetters(self, s: str) -> str:
    ls = list(s)
    left = 0
    right = len(ls) - 1

    while left<right:
        if not ls[right].isalpha():
            right -= 1
        elif not ls[left].isalpha():
            left += 1
        else:
            ls[left], ls[right] = ls[right],ls[left]
            left += 1
            right -= 1

    return "".join(ls)
```

## <https://github.com/kaestro/algorithms_v3/commit/d161bedc68860e2703255935f6b08fe27ad5d8b4>

* c.swapcase()를 이용하면 대소문자를 바꿀 수 있다.
* 반대의 것이 존재하지 않는다면, substring에 본인은 포함되지 않고, 정답은 이 것의 좌측에 있는 substring과 우측에 있는 substring 중 하나라는 의미이다.
* 이 때문에 divide and conquer를 이용하여 풀 수 있다.

---

## <https://github.com/kaestro/algorithms_v3/commit/c91f158c1d998989222aa9ed8823dc06a05e6f64>

* sort를 작은 값부터 해야 한다는 편견을 벗어나라.

---

## <https://github.com/kaestro/algorithms_v3/commit/4bbb4cf6c84636a168b4b0ae7ea260d540eb0af0>

* 저장하는 것은 가능한 미뤄라.

---

## <https://github.com/kaestro/algorithms_v3/commit/5afe0a7ea88e7eca2f75c93213da15d453bc50fb>

* find kth omitted integer
* 이진탐색을 이용할 때, 핵심은 mid이다.

---

## <https://github.com/kaestro/algorithms_v3/commit/fe2f1aa261ba529229b250d28f2c0c556c3f484d>

* MatrixBlockSum problem
* prefixsum을 통한 dp로 해결할 수 있다.
