# 미디어 쿼리 및 반응형 디자인 가이드

Less를 사용하여 반응형 디자인을 구현하는 방법을 설명합니다. 이 문서에서는 미디어 쿼리를 사용하여 다양한 화면 크기에 대응하는 스타일을 작성하는 방법과 Less 믹스인을 활용한 반응형 디자인 관리 전략을 다룹니다.

## 1. 미디어 쿼리 사용법

### 1.1. 기본적인 미디어 쿼리
미디어 쿼리는 화면 크기나 해상도에 따라 다른 스타일을 적용할 수 있는 방법입니다.

```
body {
  background-color: white;

  @media (max-width: 600px) {
    background-color: gray;
  }
}
```

위 예제에서는 화면 폭이 600px 이하일 때 배경색을 회색으로 변경합니다.

### 1.2. Less에서 미디어 쿼리 믹스인 활용
Less에서는 자주 사용하는 미디어 쿼리를 믹스인으로 정의하여 재사용할 수 있습니다.

```
.respond-to(@breakpoint) {
  @media (max-width: @breakpoint) { 
    @content; 
  }
}

.container {
  width: 100%;

  .respond-to(600px) {
    width: 50%;
  }
}
```

## 2. 믹스인으로 반응형 디자인 관리

### 2.1. 브레이크포인트 설정
Less를 사용하여 공통 브레이크포인트를 변수로 설정하고, 모든 스타일에서 일관되게 사용할 수 있습니다.

```
@breakpoints: {
  small: 600px;
  medium: 900px;
  large: 1200px;
};

.respond-to(@breakpoint) {
  @media (max-width: @breakpoint) { 
    @content; 
  }
}

.header {
  font-size: 20px;

  .respond-to(@breakpoints[small]) {
    font-size: 16px;
  }
}
```

### 2.2. 그리드 시스템 구현
Less를 사용하여 반응형 그리드 시스템을 쉽게 구현할 수 있습니다.

```
.span-columns(@columns, @total-columns: 12) {
  width: percentage(@columns / @total-columns);
}

.column {
  .span-columns(6); // 50% 너비
}
```

## 3. 반응형 디자인 최적화

### 3.1. 최소한의 미디어 쿼리 사용
모든 스타일에 미디어 쿼리를 적용하는 대신, 필요한 곳에서만 사용하여 성능을 최적화합니다.

### 3.2. 미디어 쿼리의 중복 제거
비슷한 미디어 쿼리를 그룹화하여 코드 중복을 줄이고, 스타일 시트의 크기를 줄입니다.

```
.respond-to(@breakpoint) {
  @media (max-width: @breakpoint) { 
    @content; 
  }
}

.container, .header {
  .respond-to(600px) {
    padding: 10px;
  }
}
```

## 4. 결론

Less를 사용한 반응형 디자인은 효율적인 미디어 쿼리 관리와 그리드 시스템 구현을 통해 다양한 화면 크기에서 일관된 사용자 경험을 제공합니다. 이 문서에서 설명한 방법을 활용하여, 반응형 디자인을 더 쉽게 구현하고 관리하세요.
