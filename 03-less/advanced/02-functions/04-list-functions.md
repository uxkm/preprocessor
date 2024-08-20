# Less 리스트 함수 (List Functions) 가이드

Less의 리스트 함수는 스타일 시트에서 리스트 데이터를 조작하는 데 유용한 도구입니다. 이 문서에서는 Less에서 제공하는 다양한 리스트 함수와 그 사용법을 설명합니다.

## 리스트 함수 (List Functions)란?

Less 리스트 함수는 리스트 데이터의 항목을 추가, 제거, 변환하거나 리스트 간의 작업을 수행할 수 있게 해주는 도구입니다.

### 주요 리스트 함수 소개

#### `length(@list)`

`length` 함수는 리스트의 항목 수를 반환합니다.

```
@colors: red, green, blue;

.count {
  content: length(@colors); // 3
}
```

#### `nth(@list, @n)`

`nth` 함수는 리스트에서 `@n` 번째 항목을 반환합니다.

```
@colors: red, green, blue;

.second-color {
  color: nth(@colors, 2); // green
}
```

#### `join(@list1, @list2, [@separator])`

`join` 함수는 두 리스트를 하나로 결합합니다.

```
@colors1: red, green;
@colors2: blue, yellow;

.all-colors {
  content: join(@colors1, @colors2); // red, green, blue, yellow
}
```

## 결론

Less 리스트 함수는 스타일 시트에서 리스트 데이터를 효율적으로 처리할 수 있게 해주는 유용한 도구입니다. 이 문서에서 소개한 리스트 함수를 사용하여, 더 유연한 데이터 관리를 구현해보세요.
