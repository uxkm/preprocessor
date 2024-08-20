# Sass 문자열 함수 (String Functions) 가이드

Sass의 문자열 함수는 CSS 스타일 시트에서 문자열을 조작하는 데 유용한 도구입니다. 이 문서에서는 Sass에서 제공하는 다양한 문자열 함수와 그 사용법을 설명합니다.

## 문자열 함수 (String Functions)란?

Sass 문자열 함수는 문자열을 조작하거나 변환하는 데 사용됩니다. 이를 통해 CSS 속성 값의 문자열을 동적으로 생성하거나 변경할 수 있습니다.

### 주요 문자열 함수 소개

#### `str-length($string)`

`str-length` 함수는 문자열의 길이를 반환합니다.

```
$font-family: 'Helvetica';

body {
  content: str-length($font-family); // 9
}
```

#### `str-insert($string, $insert, $index)`

`str-insert` 함수는 지정된 위치에 문자열을 삽입합니다.

```
$font-family: 'Helvetica';

body {
  font-family: str-insert($font-family, ', Arial', 9); // 'Helvetica, Arial'
}
```

#### `str-index($string, $substring)`

`str-index` 함수는 특정 부분 문자열이 처음으로 나타나는 위치를 반환합니다.

```
$font-family: 'Helvetica';

body {
  content: str-index($font-family, 'e'); // 2
}
```

#### `str-slice($string, $start-at, $end-at)` 

`str-slice` 함수는 문자열의 부분 문자열을 반환합니다.

```
$font-family: 'Helvetica';

body {
  content: str-slice($font-family, 1, 4); // 'Hell'
}
```

#### `to-upper-case($string)` / `to-lower-case($string)`

이 함수들은 각각 문자열을 대문자 또는 소문자로 변환합니다.

```
$font-family: 'Helvetica';

body {
  content: to-upper-case($font-family); // 'HELVETICA'
  content: to-lower-case($font-family); // 'helvetica'
}
```

## 결론 - Sass 문자열 함수로 텍스트 조작하기

Sass 문자열 함수는 CSS 스타일 시트에서 문자열을 효율적으로 처리하고 변환할 수 있게 해주는 강력한 도구입니다. 이 문서에서 소개한 문자열 함수를 사용하여 더 유연하고 동적인 스타일을 작성해보세요.
