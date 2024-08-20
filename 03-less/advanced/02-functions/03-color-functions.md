# Less 색상 함수 (Color Functions) 가이드

Less의 색상 함수는 CSS 스타일 시트에서 색상을 조작하는 데 유용한 도구입니다. 이 문서에서는 Less에서 제공하는 다양한 색상 함수와 그 사용법을 설명합니다.

## 색상 함수 (Color Functions)란?

Less 색상 함수는 색상의 밝기, 채도, 투명도 등을 조절하거나, 색상 간의 변화를 계산할 수 있는 도구입니다.

### 주요 색상 함수 소개

#### `lighten(@color, @amount)` / `darken(@color, @amount)`

이 함수들은 각각 색상을 밝게 또는 어둡게 만듭니다.

```
@primary-color: #3498db;

.light {
  background-color: lighten(@primary-color, 10%); // 밝게
}

.dark {
  background-color: darken(@primary-color, 10%); // 어둡게
}
```

#### `saturate(@color, @amount)` / `desaturate(@color, @amount)`

이 함수들은 색상의 채도를 증가시키거나 감소시킵니다.

```
@primary-color: #3498db;

.saturated {
  background-color: saturate(@primary-color, 20%); // 채도 증가
}

.desaturated {
  background-color: desaturate(@primary-color, 20%); // 채도 감소
}
```

#### `fadein(@color, @amount)` / `fadeout(@color, @amount)`

이 함수들은 색상의 투명도를 조절합니다.

```
@primary-color: #3498db;

.transparent {
  background-color: fadeout(@primary-color, 0.3); // 투명하게
}

.opaque {
  background-color: fadein(@primary-color, 0.3); // 불투명하게
}
```

#### `mix(@color1, @color2, [@weight])`

`mix` 함수는 두 색상을 혼합하여 새로운 색상을 생성합니다.

```
@color1: #ff0000;
@color2: #0000ff;

.mixed {
  background-color: mix(@color1, @color2, 50%); // 보라색
}
```

## 결론

Less 색상 함수는 스타일 시트에서 색상을 다양하게 조작할 수 있는 강력한 도구입니다. 이 문서에서 소개한 색상 함수를 사용하여, 더 생동감 있고 유연한 디자인을 구현해보세요.
