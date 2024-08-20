# Less 믹스인 (Mixins) 사용 가이드 - 코드 재사용성 극대화

Less에서 믹스인(Mixins)은 자주 사용되는 스타일 블록을 재사용할 수 있도록 해주는 기능으로, 코드의 중복을 줄이고 유지보수성을 높이는 데 매우 유용합니다. 이 문서에서는 Less 믹스인을 정의하고 사용하는 방법을 소개합니다.

## Less 믹스인이란?

Less 믹스인은 CSS 스타일을 함수처럼 정의하고, 필요할 때마다 호출하여 사용할 수 있습니다. 이를 통해 반복적인 스타일 작업을 간소화하고, 코드의 재사용성을 극대화할 수 있습니다.

### 믹스인 정의와 사용

믹스인은 클래스와 유사하게 정의하며, 필요할 때 이를 호출하여 사용할 수 있습니다.

```
.border-radius(@radius) {
  -webkit-border-radius: @radius;
     -moz-border-radius: @radius;
          border-radius: @radius;
}

.box {
  .border-radius(10px);
}
```

위 예제에서는 `border-radius` 믹스인을 정의하여, `.box` 클래스에 적용하고 있습니다. 이 믹스인은 여러 요소에서 재사용될 수 있습니다.

### 믹스인에 인자 전달

Less 믹스인은 인자를 받아 동적으로 스타일을 생성할 수 있습니다. 기본 인자 값도 설정할 수 있어, 유연한 스타일 작성이 가능합니다.

```
.box-shadow(@x: 0px, @y: 0px, @blur: 5px, @color: rgba(0, 0, 0, 0.5)) {
  -webkit-box-shadow: @x @y @blur @color;
          box-shadow: @x @y @blur @color;
}

.panel {
  .box-shadow(2px, 4px);
}
```

위 예제에서는 기본 인자를 정의하여, 필요에 따라 특정 값을 재정의할 수 있습니다.

## 결론

Less 믹스인은 코드의 재사용성을 극대화하고, 유지보수성을 높이는 데 중요한 역할을 합니다. 이 문서에서 소개한 믹스인 사용법을 활용하여, 효율적인 스타일 시트를 작성해보세요.
