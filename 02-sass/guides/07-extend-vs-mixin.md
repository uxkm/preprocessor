# Sass @extend와 @mixin의 적절한 사용법

Sass는 스타일 시트에서 재사용성을 높이기 위해 `@extend`와 `@mixin`을 제공합니다. 이 문서에서는 이 두 기능의 차이점과 각 기능을 언제 사용해야 하는지에 대해 설명합니다.

## 1. @extend와 @mixin의 차이점

### 1.1. @extend
`@extend`는 선택자의 스타일을 다른 선택자에 상속하여 재사용하는 방법입니다. 여러 선택자가 같은 스타일을 공유할 때 유용합니다.

```
.button {
  padding: 10px;
  border-radius: 5px;
}

.primary-button {
  @extend .button;
  background-color: blue;
}

.secondary-button {
  @extend .button;
  background-color: gray;
}
```

위 예제에서 `.primary-button`과 `.secondary-button`은 `.button`의 스타일을 상속받습니다.

### 1.2. @mixin
`@mixin`은 재사용 가능한 스타일 블록을 정의하여, 필요할 때마다 이를 호출할 수 있습니다. 변수를 사용해 동적으로 스타일을 생성할 수 있습니다.

```
@mixin button-style($color) {
  padding: 10px;
  border-radius: 5px;
  background-color: $color;
}

.primary-button {
  @include button-style(blue);
}

.secondary-button {
  @include button-style(gray);
}
```

## 2. 언제 @extend를 사용해야 할까?

### 2.1. 공통 스타일 상속이 필요할 때
여러 선택자가 동일한 스타일을 가져야 할 때 `@extend`를 사용합니다. 이는 코드 중복을 줄이고, 스타일 시트의 크기를 줄이는 데 유용합니다.

### 2.2. 선택자 그룹화
`@extend`는 여러 선택자를 하나의 그룹으로 묶어 스타일을 적용할 때 유용합니다. 이로 인해 CSS 출력이 간결해집니다.

```
.alert {
  padding: 10px;
  border: 1px solid red;
}

.error {
  @extend .alert;
}

.warning {
  @extend .alert;
}
```

위의 예제는 하나의 `.alert` 스타일 블록을 공유하는 두 개의 선택자를 만듭니다.

## 3. 언제 @mixin을 사용해야 할까?

### 3.1. 동적 스타일 생성이 필요할 때
`@mixin`은 인자를 받아 동적으로 스타일을 생성할 수 있습니다. 다양한 상황에서 다양한 값을 사용하여 스타일을 적용할 때 유용합니다.

### 3.2. 중복을 줄이면서 코드 재사용
`@mixin`을 사용하면 코드 중복을 줄이면서, 다양한 스타일 블록을 재사용할 수 있습니다.

```
@mixin text-style($font-size, $color) {
  font-size: $font-size;
  color: $color;
}

.header {
  @include text-style(20px, blue);
}

.footer {
  @include text-style(16px, gray);
}
```

## 4. 성능 고려 사항

### 4.1. @extend의 성능 이슈
`@extend`를 과도하게 사용하면, 예상치 못한 스타일 상속이 발생하여 CSS 출력이 비대해질 수 있습니다. 특히, 여러 선택자가 `@extend`를 공유할 때 CSS 출력이 복잡해질 수 있습니다.

### 4.2. @mixin의 성능 고려
`@mixin`은 호출될 때마다 스타일을 반복 생성하기 때문에, 지나치게 사용하면 CSS 파일의 크기가 커질 수 있습니다. 따라서 적절히 사용해야 합니다.

## 5. 결론

Sass에서 `@extend`와 `@mixin`은 각각의 장단점이 있으며, 상황에 맞게 적절히 사용해야 합니다. 일반적으로 공통 스타일 상속에는 `@extend`를, 동적 스타일 생성에는 `@mixin`을 사용하는 것이 좋습니다. 성능 고려 사항을 염두에 두고, 프로젝트에 맞는 방식을 선택하세요.
