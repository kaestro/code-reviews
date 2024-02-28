# Head first design patterns in go

## https://github.com/kaestro/head-first-design-pattern-in-go/commit/c6f1841a62e8f791b568bf6f813e0380a132e970

```go
type Duck interface {
    Quack()
    Fly()
    Display()
}

type DuckBehavior struct {
}

func (d *DuckBehavior) Quack() {
    fmt.Println("Quack")
}

func (d *DuckBehavior) Fly() {
    fmt.Println("Fly")
}

type MallardDuck struct {
    DuckBehavior
}

func (m *MallardDuck) Display() {
    fmt.Println("MallardDuck")
}
```

와 같은 식으로 일부만 구현하고, 나머지는 상속받은 객체에서 구현하도록 넘길 수 있다. MallardDuck에서 DuckBehavior의 구현된 메소드를 그대로 가져다 사용하는 것을 embedding이라고 한다.

이를 명시적인 객체로 따로 선언시 composition이라고 한다.


---


## https://github.com/kaestro/head-first-design-pattern-in-go/commit/c180fccc61392edcac1245c7a82925780db50a79

### go 에서 slice를 삭제하는 법

```go
sampleSlice := []int{1, 2, 3, 4, 5}
sampleSlice = append(sampleSlice[:2], sampleSlice[3:]...)
```

이 때 slice의 후반부는 sampleSlice[3:]가 아니라 sampleSlice[3:]...를 사용하는데, 이는 전자를 사용할 경우 슬라이스 내부의 슬라이스를 리턴하게 되어 에러가 발생한다. 이를 풀어서 리턴하기 위해 ...를 사용한다.

이는 파이썬에서 파라미터로 무엇이 들어올지 모를 때 받기 위해
```python
def sampleMethod(*args, **kargs):
```

를 사용하는 것과 비슷하다.

### go에서 slice를 순회하는 법

```go
for i, v := range sampleSlice {
    fmt.Println(i, v)
}
```

파이썬과 유사하다.

### go에서 parameter로 interface{}를 받는 다는 것

go에서는 interface{}를 받는다는 것은 모든 타입을 받을 수 있다는 것을 의미한다. 이는 파이썬의 *args와 유사하다.

이 때문에 인터페이스로 상속받은 객체를 받아서 해당 객체에 대한 메소드를 호출할 수 있다. 대신, type assertion을 통해 해당 객체의 타입을 확인하고, 해당 객체의 메소드를 호출해야 한다.

```go
type Observer interfae {
    Update(subject interface{})
}

type WeatherData struct {
    temperature float64
    humidity float64
    pressure float64
    observers []Observer
}

func (w *WeatherData) NotifyObservers() {
    for _, observer := range w.observers {
        observer.Update(w)
    }
}

type CurrentConditionDisplay struct {
    temperature float64
    humidity float64
}

func (c *CurrentConditionDisplay) Update(subject interface{}) {
    weatherData, ok := subject.(*WeatherData)
    if ok {
        c.temperature = weatherData.temperature
        c.humidity = weatherData.humidity
    }
}

type StatisticsDisplay struct {
    temperature float64
    humidity float64
}

func (s *StatisticsDisplay) Update(subject interface{}) {
    weatherData, ok := subject.(*WeatherData)
    if ok {
        s.temperature = weatherData.temperature
        s.humidity = weatherData.humidity
    }
}
```

이 경우에는 추후에 새로운 형태의 subject가 추가됐을 때에 유용하게 사용할 수 있다. 예를 들어 TrafficData라는 subject가 추가됐을 경우에, 현재 observer에서 TrafficData를 받아서 처리할 수 있게 된다.

```go
type TrafficData struct {
    traffic int
}

func (t *TrafficData) NotifyObservers() {
    for _, observer := range t.observers {
        observer.Update(t)
    }
}

type CurrentConditionDisplay struct {
    temperature float64
    humidity float64
    traffic int
}

func (c *CurrentConditionDisplay) Update(subject interface{}) {
    if weatherData, ok := subject.(*WeatherData); ok {
        c.temperature = weatherData.temperature
        c.humidity = weatherData.humidity
    } else if trafficData, ok := subject.(*TrafficData); ok {
        c.traffic = trafficData.traffic
    }
}
```