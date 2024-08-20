# Sass에서의 테마 관리

Sass를 사용하여 다중 테마를 관리하는 방법을 설명합니다. 다중 테마 지원은 특히 브랜드 웹사이트나 어플리케이션에서 중요한 역할을 합니다. 이 문서에서는 테마별 변수 설정, 믹스인 활용, 성능 최적화 방법 등을 다룹니다.

## 1. 다중 색상 테마 설정

### 1.1. 테마 변수 설정
테마별로 변수를 정의하고, 이를 기반으로 스타일을 적용합니다.

```
$light-theme: (
  primary: #3498db,
  secondary: #2ecc71,
  background: #ffffff
);

$dark-theme: (
  primary: #2c3e50,
  secondary: #8e44ad,
  background: #34495e
);

$theme: $light-theme; // 현재 테마 설정

body {
  background-color: map-get($theme, background);
}
```

### 1.2. 테마 전환
테마 전환 시, 변수의 값을 변경하여 전체 스타일을 업데이트할 수 있습니다.

```
$theme: $dark-theme; // 테마 전환

body {
  background-color: map-get($theme, background);
}
```

## 2. 테마별 재사용 가능한 변수 및 믹스인 설정

### 2.1. 공통 믹스인 사용
테마별로 동일한 스타일이 반복적으로 사용될 경우, 공통 믹스인을 정의하여 코드 중복을 줄일 수 있습니다.

```
@mixin theme-colors($theme) {
  background-color: map-get($theme, background);
  color: map-get($theme, primary);
}

.header {
  @include theme-colors($theme);
}
```

### 2.2. 테마별 특정 스타일 관리
특정 스타일은 테마별로 다르게 적용될 수 있으므로, 테마별 스타일 블록을 별도로 정의합니다.

```
.light-theme {
  @include theme-colors($light-theme);
}

.dark-theme {
  @include theme-colors($dark-theme);
}
```

## 3. 테마 전환 시 성능 최적화

### 3.1. CSS 파일 분할
테마별로 CSS 파일을 분할하여, 필요한 테마의 파일만 로드하도록 설정합니다. 이를 통해 초기 로딩 시간을 줄일 수 있습니다.

### 3.2. 조건부 로드
조건부 로드를 통해 사용자의 선호도에 따라 테마를 로드할 수 있습니다. 예를 들어, 사용자가 다크 모드를 선택하면 다크 테마 CSS를 로드합니다.

## 4. 결론

Sass를 사용하여 다중 테마를 관리하면, 다양한 스타일 옵션을 효율적으로 제공할 수 있습니다. 이 문서에서 설명한 테마 관리 전략을 활용하여, 사용자 경험을 개선하고 코드의 재사용성을 극대화하세요.
