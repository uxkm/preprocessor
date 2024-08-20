# Sass 변수(Variables) 사용법 - 스타일 시트 효율성 극대화

Sass에서 변수를 사용하면 스타일 시트의 유지보수성과 재사용성이 크게 향상됩니다. 이 문서에서는 Sass 변수를 정의하고 사용하는 방법, 그리고 이를 통해 스타일 시트를 더 효율적으로 관리하는 방법을 살펴보겠습니다.

## Sass 변수란? - CSS 스타일의 핵심 요소

Sass에서 변수는 자주 사용되는 스타일 값(예: 색상, 크기, 폰트 등)을 저장하고, 코드 전체에서 재사용할 수 있도록 해줍니다. 이를 통해 코드의 일관성과 유지보수성을 높일 수 있습니다.

### Sass 변수의 정의와 사용

Sass 변수는 `$` 기호로 시작하며, 원하는 값을 지정할 수 있습니다. 변수는 스타일 시트 전반에 걸쳐 사용될 수 있습니다.

```
$primary-color: #3498db;
$secondary-color: #2ecc71;
$font-stack: Helvetica, sans-serif;

body {
  color: $primary-color;
  font-family: $font-stack;
}
```

위 예제에서는 `$primary-color`, `$secondary-color`, `$font-stack` 변수를 정의하고, 이 변수를 `body` 스타일에서 사용하였습니다.

## Sass 변수 활용 팁

### 변수의 유효 범위와 재정의

Sass 변수는 전역 또는 지역 스코프(scope)를 가질 수 있습니다. 변수를 선언한 위치에 따라 유효 범위가 결정됩니다. 또한, 변수를 다른 변수로 재정의할 수 있어, 스타일을 동적으로 변경할 수 있습니다.

```
$global-color: #333;

.section {
  $local-color: #555;
  color: $local-color;
}

.footer {
  color: $global-color;
}
```

### Sass 변수의 재사용성을 극대화하는 방법

Sass 변수는 특히 반복적인 스타일을 관리하는 데 유용합니다. 색상 팔레트, 폰트 크기, 공간 크기 등 프로젝트 전반에서 자주 사용되는 값을 변수로 관리하면, 코드 유지보수가 훨씬 수월해집니다.

```
$padding-small: 5px;
$padding-medium: 10px;
$padding-large: 20px;

.container {
  padding: $padding-medium;
}
```

## 결론 - Sass 변수를 사용하여 CSS 스타일 시트 최적화

Sass 변수는 스타일 시트에서 코드의 일관성을 유지하고, 유지보수를 쉽게 해주는 강력한 도구입니다. 이 문서에서 설명한 변수 사용법을 통해 스타일 시트를 더욱 효율적으로 관리해보세요. 프로젝트의 규모가 커질수록 Sass 변수가 가져다주는 이점을 크게 느낄 수 있을 것입니다.
