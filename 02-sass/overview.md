# Sass 소개 및 기본 사용법 가이드

Sass(Syntactically Awesome Stylesheets)는 CSS 전처리기 중 가장 널리 사용되는 도구로, 스타일 시트 작성의 효율성을 극대화하고 유지보수성을 향상시키는 기능을 제공합니다. 이 문서에서는 Sass의 개요와 기본 사용법에 대해 자세히 알아보겠습니다.

## Sass란 무엇인가? - CSS 전처리기

Sass는 CSS의 단순한 확장판이 아니라, 변수를 사용하여 색상, 크기 등을 관리하고, 중첩(Nesting)을 통해 선택자를 더 구조화하며, 믹스인(Mixins)과 상속(Inheritance) 기능을 통해 코드의 재사용성을 높일 수 있는 도구입니다. 이 모든 기능은 스타일 시트 작성의 생산성을 크게 향상시킵니다.

### Sass의 두 가지 문법: Sass와 SCSS

Sass는 두 가지 문법을 제공합니다:
- **Sass 문법**: 중괄호와 세미콜론이 필요 없는 간결한 문법.
- **SCSS 문법**: CSS와 완전히 호환되며, 기존 CSS 파일을 확장하여 사용할 수 있습니다.

SCSS 문법이 더 친숙할 수 있으므로, 대부분의 새로운 프로젝트에서는 SCSS 문법이 사용됩니다.

```
$primary-color: #3498db;

body {
  background-color: $primary-color;
}
```

## Sass의 주요 기능 소개

### 1. 변수(Variables) 사용

Sass에서는 변수를 사용하여 스타일 시트에서 반복적으로 사용되는 값들을 쉽게 관리할 수 있습니다. 변수를 사용하면 코드의 재사용성이 높아지고, 유지보수가 쉬워집니다.

```
$font-stack: Helvetica, sans-serif;
$primary-color: #333;

body {
  font-family: $font-stack;
  color: $primary-color;
}
```

### 2. 중첩(Nesting) 기능

Sass는 중첩 기능을 제공하여, 선택자 간의 관계를 명확하게 표현할 수 있습니다. 이를 통해 CSS 선택자 작성이 더욱 직관적이고 가독성이 높아집니다.

```
nav {
  ul {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  li { display: inline-block; }

  a {
    color: $primary-color;
    text-decoration: none;
  }
}
```

### 3. 믹스인(Mixins) 활용

Sass 믹스인은 자주 사용하는 스타일 블록을 재사용할 수 있도록 해주는 기능입니다. 이를 통해 코드 중복을 줄이고, 유지보수성을 향상시킬 수 있습니다.

```
@mixin border-radius($radius) {
  -webkit-border-radius: $radius;
     -moz-border-radius: $radius;
          border-radius: $radius;
}

.box { @include border-radius(10px); }
```

## 결론 - Sass로 스타일 시트를 효율적으로 관리하기

Sass는 CSS의 강력한 확장 도구로, 변수, 중첩, 믹스인 등의 기능을 통해 스타일 시트를 더욱 효율적으로 작성하고 관리할 수 있습니다. 이 문서에서 소개한 기본 기능을 이해하고, 실제 프로젝트에서 활용해보세요. Sass를 사용하면 스타일 시트 관리가 훨씬 더 쉬워질 것입니다.
