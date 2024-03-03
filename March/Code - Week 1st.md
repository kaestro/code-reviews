# Algorithms_v3

## https://github.com/kaestro/algorithms_v3/commit/b8068cfdfebd4b77addcfe5fe3c7089e3c7d9968
: BFS와 Hashing을 같이 사용한 문제.

1. bfs를 통해 그루핑이 된 영역을 map에다가 id 통해 tagging하고, 해당 크기를 dictionary(hashmap)에 저장한다.
2. 시추할 때 영역을 확인하면서, 뚫린 영역일 경우 이미 visited 됐는지 확인하기 위한 set을 만들어서 확인하고, 없을 경우 더한다.

---

## https://github.com/kaestro/algorithms_v3/commit/4ed1eff991f9225bb754bf8b63b2e0a46675b1af
: python에서 dictionary를 looping하는 방법
## https://github.com/kaestro/algorithms_v3/commit/650bcf108eb80cfd52731562e93803c3e42a6ed8
: python에서 dictionary를 삭제하지 않고 looping하는 방법

heap을 이용하는 코드도 아예 안에서 loop 안하고 맨 앞의 값을 비교하는 방식으로 구현했으면 충분히 동작할 수도 있었음. 대신 이러느니 그냥 sorted queue를 쓰는게 나았을 것.

```python
while section_dict:
    min_section = min(section_dict)
    to_delete = [i for i in range(min_section, min(min_section + roller_length, wall_length)) if i in section_dict]
    for i in to_delete:
        del section_dict[i]
```

```python
for section in sorted(section_dict):
    if section_dict[section] == 0:
        for i in range(section, min(section + roller_length, wall_length)):
            if i in section_dict:
                section_dict[i] = 1
```

---

# Head First Design Patterns in Go

## https://github.com/kaestro/head-first-design-pattern-in-go/commit/74657696906f84af720d9a75f658107b933b9557#diff-c98c4f6900025d63a3c119abc33c9a199b3ba91fe762f34bf5d5eebc66a2aee1
: Go에서 템플릿 메소드 패턴을 구현하는 방법

Go에서는 interface를 implement할 때, 일부만 구현하고 하위 클래스에서 구현하도록 할 수 있다.

```go
type Beverage interface {
    BoilWater()
    Brew()
    PourInCup()
    AddCondiments()
}

type CaffeineBeverage struct {
    Beverage
}

func (c *CaffeineBeverage) BoilWater() {
    fmt.Println("Boiling water")
}

func (c *CaffeineBeverage) PourInCup() {
    fmt.Println("Pouring into cup")
}

type Tea struct {
    CaffeineBeverage
}

func (t *Tea) Brew() {
    fmt.Println("Steeping the tea")
}

func (t *Tea) AddCondiments() {
    fmt.Println("Adding Lemon")
}

---