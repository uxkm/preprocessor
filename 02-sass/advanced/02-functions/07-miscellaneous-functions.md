# Sass 차원 함수 (Miscellaneous Functions) 가이드

Sass의 차원 함수는 스타일 시트에서 단위 관련 작업을 수행하는 데 유용한 도구입니다. 이 문서에서는 Sass에서 제공하는 다양한 차원 함수와 그 사용법을 설명합니다.

## 차원 함수 (Miscellaneous Functions)란?

Sass 차원 함수는 단위를 처리하거나, 값의 차원을 변환하는 등의 작업을 수행할 수 있는 도구입니다.

### 주요 차원 함수 소개

#### `unit($number)`

`unit` 함수는 주어진 숫자의 단위를 반환합니다.

```
$value: 10px;

.unit {
  content: unit($value); // 'px'
}
```

#### `unitless($number)`

`unitless` 함수는 숫자가 단위를 가지고 있는지 여부를 확인합니다. 단위가 없으면 `true`를 반환합니다.

```
$value: 10;

.no-unit {
  content: unitless($value); // true
}
```

#### `comparable($number1, $number2)`

`comparable` 함수는 두 값이 비교 가능한지를 확인합니다. 두 값이 같은 단위를 가지거나 둘 다 단위가 없는 경우 `true`를 반환합니다.

```
$value1: 10px;
$value2: 2em;

.compatible {
  content: comparable($value1, $value2); // false
}
```

## 결론 - Sass 차원 함수로 단위 조작하기

Sass 차원 함수는 스타일 시트에서 단위를 효율적으로 관리하고 변환할 수 있게 해주는 유용한 도구입니다. 이 문서에서 소개한 차원 함수를 사용하여, 더 유연한 스타일 조작을 구현해보세요.
