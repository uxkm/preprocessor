# Sass 파셜 (Partials) 사용 가이드 - 스타일 시트의 모듈화

Sass의 파셜(Partials)은 스타일 시트를 작은 단위로 분리하여 관리할 수 있게 해주는 중요한 도구입니다. 이 문서에서는 파셜을 사용하여 스타일 시트를 모듈화하는 방법을 설명합니다.

## Sass 파셜 (Partials)이란? - 파일 분리와 모듈화

Sass 파셜은 파일 이름 앞에 밑줄(`_`)을 붙여 생성한 Sass 파일로, 컴파일 시 독립적인 CSS 파일로 생성되지 않습니다. 대신 다른 Sass 파일에서 `@import` 지시어를 사용하여 파셜 파일을 가져와 사용합니다.

### 파셜 파일 생성하기

파셜 파일은 일반 Sass 파일과 동일하게 작성되지만, 파일 이름 앞에 밑줄(`_`)을 붙여 컴파일되지 않도록 설정합니다.

예를 들어, `_variables.scss` 파일을 생성하여 프로젝트 전반에서 사용할 변수를 정의할 수 있습니다.

```
$primary-color: #3498db;
$secondary-color: #2ecc71;
```

### 파셜 파일 가져오기 - @import 지시어

`@import` 지시어를 사용하여 다른 Sass 파일에서 파셜 파일을 가져와 사용할 수 있습니다.

```
@import 'partials/_variables';

body {
  background-color: $primary-color;
}
```

위의 예제에서는 `_variables.scss` 파일을 가져와 사용하고 있습니다.

### 파셜을 통한 스타일 시트 모듈화

파셜 파일을 사용하면 스타일 시트를 기능별로 분리하여 관리할 수 있습니다. 예를 들어, `_mixins.scss`, `_buttons.scss` 등의 파일을 각각 생성하여 특정 기능을 분리할 수 있습니다.

```
@import 'partials/_mixins';
@import 'partials/_buttons';

@include border-radius(5px);

.button-primary {
  @extend .button;
  background-color: $primary-color;
}
```

이 예제에서는 믹스인과 버튼 스타일을 각각의 파셜 파일에 정의하고, 이를 가져와 사용합니다.

## 결론 - Sass 파셜로 효율적인 스타일 관리

Sass 파셜은 스타일 시트를 작은 단위로 분리하고, 각 단위를 관리할 수 있게 해주는 중요한 도구입니다. 이 문서에서 소개한 파셜 사용법을 통해, 스타일 시트를 더 효율적으로 모듈화하고 유지보수할 수 있습니다.
