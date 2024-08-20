# Less 중첩 (Nesting) 사용 가이드 - CSS 선택자 구조화

Less는 중첩(Nesting) 기능을 제공하여, CSS 선택자 간의 관계를 보다 명확하고 직관적으로 작성할 수 있도록 해줍니다. 이 문서에서는 Less의 중첩 기능을 활용하여 스타일 시트를 구조화하고, 유지보수를 용이하게 하는 방법을 설명합니다.

## Less 중첩이란?

Less의 중첩 기능은 HTML 구조를 반영하여 CSS 선택자를 계층적으로 작성할 수 있게 해줍니다. 이를 통해 코드의 가독성을 높이고, 선택자 간의 관계를 쉽게 파악할 수 있습니다.

### 중첩 사용법

일반적인 CSS에서는 선택자를 일일이 작성해야 하지만, Less에서는 중첩을 사용하여 이를 간결하게 표현할 수 있습니다.

```
.navbar {
  background-color: #333;

  ul {
    list-style: none;
    margin: 0;
    padding: 0;

    li {
      display: inline-block;

      a {
        color: white;
        text-decoration: none;
      }
    }
  }
}
```

위의 Less 코드에서 `.navbar` 내부의 모든 요소는 HTML 구조를 반영하여 중첩되어 있습니다. 이 방식은 CSS 선택자의 관계를 더 명확하게 만들어줍니다.

## 부모 선택자 참조 (&)

Less에서는 `&` 기호를 사용하여 부모 선택자를 참조할 수 있습니다. 이를 통해 중첩된 선택자에서도 부모 선택자를 기반으로 한 스타일 정의가 가능합니다.

```
.button {
  background-color: #3498db;
  color: white;

  &:hover {
    background-color: darken(@button-background-color, 10%);
  }

  &-primary {
    background-color: #2980b9;
  }
}
```

위 예제에서 `&` 기호는 부모 선택자인 `.button`을 참조하여, `.button:hover`와 `.button-primary` 선택자를 정의합니다.

## 결론

Less의 중첩 기능은 CSS 선택자 간의 관계를 명확하게 표현하고, 코드의 가독성과 유지보수성을 높여줍니다. 이 문서에서 배운 중첩 기법을 활용하여, 스타일 시트를 보다 효율적으로 작성하고 관리하세요.
