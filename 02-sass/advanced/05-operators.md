# Sass 연산자 (Operators) 가이드 - 스타일 시트에서의 계산

Sass의 연산자(Operators)는 스타일 시트에서 수학적 계산과 논리적 판단을 수행할 수 있는 도구입니다. 이 문서에서는 Sass에서 제공하는 다양한 연산자와 그 사용법을 설명합니다.

## Sass 연산자 (Operators)란? - CSS 스타일 계산

Sass 연산자는 CSS 속성 값을 계산하거나, 논리적 판단을 통해 조건부 스타일을 적용하는 데 사용됩니다. 이를 통해 동적이고 유연한 스타일 시트를 작성할 수 있습니다.

### 산술 연산자 (Arithmetic Operators)

산술 연산자는 숫자 간의 기본적인 수학적 계산을 수행할 때 사용됩니다.

#### `+` (더하기)

```
$base-padding: 10px;

.container {
  padding: $base-padding + 5px; // 15px
}
```

#### `-` (빼기)

```
$base-padding: 10px;

.container {
  padding: $base-padding - 5px; // 5px
}
```

#### `*` (곱하기)

```
$base-padding: 10px;

.container {
  padding: $base-padding * 2; // 20px
}
```

#### `/` (나누기)

```
$base-padding: 10px;

.container {
  padding: $base-padding / 2; // 5px
}
```

### 비교 연산자 (Comparison Operators)

비교 연산자는 두 값을 비교하여 논리적 판단을 내리는 데 사용됩니다.

#### `==` (같음) / `!=` (다름)

```
$color1: #fff;
$color2: #000;

.test {
  @if $color1 == $color2 {
    content: 'Colors are the same';
  } @else {
    content: 'Colors are different';
  }
}
```

#### `<` (작음) / `>` (큼) / `<=` (작거나 같음) / `>=` (크거나 같음)

```
$width1: 100px;
$width2: 200px;

.test {
  @if $width1 > $width2 {
    content: 'Width1 is greater';
  } @else {
    content: 'Width2 is greater';
  }
}
```

### 논리 연산자 (Logical Operators)

논리 연산자는 조건을 결합하여 복합적인 논리 판단을 내리는 데 사용됩니다.

#### `and` (그리고) / `or` (또는) / `not` (부정)

```
$condition1: true;
$condition2: false;

.test {
  @if $condition1 and not $condition2 {
    content: 'Condition met';
  }
}
```

## 결론 - Sass 연산자로 동적 스타일 구현하기

Sass 연산자는 스타일 시트에서 수학적 계산과 논리적 판단을 효율적으로 처리할 수 있게 해주는 강력한 도구입니다. 이 문서에서 소개한 연산자를 사용하여, 더 유연하고 동적인 스타일 시트를 작성해보세요.
