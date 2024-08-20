# Less 문자열 함수 (String Functions) 가이드

Less의 문자열 함수는 CSS 스타일 시트에서 문자열을 조작하는 데 유용한 도구입니다. 이 문서에서는 Less에서 제공하는 다양한 문자열 함수와 그 사용법을 설명합니다.

## 문자열 함수 (String Functions)란?

Less 문자열 함수는 문자열을 조작하거나 변환하는 데 사용됩니다. 이를 통해 CSS 속성 값의 문자열을 동적으로 생성하거나 변경할 수 있습니다.

### 주요 문자열 함수 소개

#### `string-length(@string)`

`string-length` 함수는 문자열의 길이를 반환합니다.

```
@font-family: 'Helvetica';

body {
  content: string-length(@font-family); // 9
}
```

#### `string-insert(@string, @insert, @index)`

`string-insert` 함수는 지정된 위치에 문자열을 삽입합니다.

```
@font-family: 'Helvetica';

body {
  font-family: string-insert(@font-family, ', Arial', 9); // 'Helvetica, Arial'
}
```

#### `string-extract(@string, @start, @end)`

`string-extract` 함수는 문자열의 부분 문자열을 반환합니다.

```
@font-family: 'Helvetica';

body {
  content: string-extract(@font-family, 1, 4); // 'Hell'
}
```

## 결론

Less 문자열 함수는 CSS 스타일 시트에서 문자열을 효율적으로 처리하고 변환할 수 있게 해주는 강력한 도구입니다. 이 문서에서 소개한 문자열 함수를 사용하여 더 유연하고 동적인 스타일을 작성해보세요.
