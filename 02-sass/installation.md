
# Sass 설치 가이드 - CSS 전처리기 설치 및 설정

Sass(Syntactically Awesome Stylesheets)는 강력한 CSS 전처리기로, 스타일 시트 작성의 효율성을 크게 높여줍니다. 이 문서에서는 Sass를 설치하고, 기본적인 설정을 하는 방법을 설명합니다.

## Sass 설치 방법 - CSS 전처리기 시작하기

Sass는 여러 가지 방법으로 설치할 수 있으며, 프로젝트의 필요에 따라 적절한 방법을 선택할 수 있습니다. 가장 일반적인 설치 방법은 npm(Node Package Manager)을 사용하는 것입니다.

### npm을 사용한 Sass 설치

npm은 Node.js 환경에서 Sass를 설치하고 관리하는 가장 일반적인 방법입니다. 아래의 명령어를 사용하여 Sass를 설치할 수 있습니다.

```
npm install -g sass
```

이 명령어는 Sass를 전역적으로 설치하여, 어디서나 Sass 명령어를 사용할 수 있게 해줍니다.

### 프로젝트 로컬 설치

프로젝트별로 Sass를 관리하려면 로컬 설치를 선택할 수 있습니다. 이는 프로젝트마다 다른 Sass 버전을 사용할 때 유용합니다.

```
npm install --save-dev sass
```

이 명령어는 프로젝트의 `node_modules` 폴더에 Sass를 설치합니다.

### Ruby를 사용한 Sass 설치

Sass는 원래 Ruby로 작성되었기 때문에, Ruby 환경에서도 쉽게 설치할 수 있습니다. 아래의 명령어를 사용하여 Sass를 설치할 수 있습니다.

```
gem install sass
```

이 방법은 Ruby 기반 프로젝트에서 주로 사용됩니다.

## Sass 컴파일러 설정

Sass 파일을 CSS로 변환하려면 컴파일러가 필요합니다. npm 또는 Ruby를 통해 설치한 Sass는 CLI(Command Line Interface)를 통해 사용할 수 있으며, 아래와 같은 명령어로 Sass 파일을 컴파일할 수 있습니다.

```
sass source/styles.scss:dist/styles.css
```

위 명령어는 `source/styles.scss` 파일을 `dist/styles.css` 파일로 컴파일합니다.

### Sass 컴파일 자동화

Sass 파일을 수동으로 컴파일하는 대신, 파일이 변경될 때마다 자동으로 컴파일하도록 설정할 수 있습니다. 아래의 명령어를 사용하면 Sass가 파일 변경을 감시하고 자동으로 컴파일합니다.

```
sass --watch source/styles.scss:dist/styles.css
```

이 명령어는 개발 과정에서 매우 유용하며, 스타일 변경 사항이 즉시 반영됩니다.

## 결론 - Sass 설치 및 설정 완료

Sass는 CSS 전처리기 중 가장 널리 사용되는 도구로, 설치와 설정이 매우 간단합니다. 이 문서에서 소개한 설치 방법을 통해 Sass를 설정하고, 프로젝트에서 효율적으로 사용할 수 있습니다. 이제 Sass를 활용하여 더 나은 스타일 시트를 작성해보세요.
