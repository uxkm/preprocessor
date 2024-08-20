# Less 숫자 함수 (Number Functions) 가이드

Less의 숫자 함수는 스타일 시트에서 수학적 계산을 쉽게 수행할 수 있도록 도와줍니다. 이 문서에서는 Less에서 제공하는 다양한 숫자 함수와 그 사용법을 설명합니다.

## 숫자 함수 (Number Functions)란?

Less 숫자 함수는 수학적 계산을 통해 동적으로 값을 생성하거나 변환할 수 있는 도구입니다. 이를 통해 스타일 시트에서 유연하게 수치를 다룰 수 있습니다.

### 주요 숫자 함수 소개

#### `percentage(@value)`

`percentage` 함수는 소수를 백분율로 변환합니다.

```
@width: 0.5;

.container {
  width: percentage(@width); // 50%
}
```

#### `round(@value)` / `ceil(@value)` / `floor(@value)`

이 함수들은 각각 값을 반올림, 올림, 내림하여 반환합니다.

```
@value: 4.67;

.rounded {
  width: round(@value); // 5
}

.ceiled {
  width: ceil(@value); // 5
}

.floored {
  width: floor(@value); // 4
}
```

#### `abs(@value)`

`abs` 함수는 주어진 값의 절대값을 반환합니다.

```
@value: -50px;

.container {
  width: abs(@value); // 50px
}
```

#### `min(@numbers...)` / `max(@numbers...)`

`min` 함수는 주어진 숫자들 중 가장 작은 값을, `max` 함수는 가장 큰 값을 반환합니다.

```
@value1: 5px;
@value2: 10px;

.smallest {
  width: min(@value1, @value2); // 5px
}

.largest {
  width: max(@value1, @value2); // 10px
}
```

## 결론

Less 숫자 함수는 스타일 시트에서 수학적 계산을 효율적으로 처리할 수 있게 해주는 유용한 도구입니다. 이 문서에서 소개한 숫자 함수를 사용하여 더욱 동적이고 유연한 스타일을 작성해보세요.
