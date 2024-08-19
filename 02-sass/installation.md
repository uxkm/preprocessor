## 애플리케이션

Mac, Windows, Linux에서 몇 분 만에 Sass를 시작할 수 있는 다양한 애플리케이션이 있습니다. 대부분의 애플리케이션은 무료로 다운로드할 수 있지만, 일부는 유료 앱입니다(그리고 충분히 가치가 있습니다).

- **CodeKit** (유료) - Mac
- **Prepros** (유료) - Mac, Windows, Linux

## 라이브러리

Sass 팀은 표준 JavaScript API를 지원하는 두 가지 Node.js 패키지를 유지 관리하고 있습니다. `sass` 패키지는 순수 JavaScript로 작성되어 약간 느리지만, Node.js가 지원하는 모든 플랫폼에 설치할 수 있습니다. `sass-embedded` 패키지는 Dart VM을 감싼 JS API로, 더 빠르지만 Windows, Mac OS, Linux만 지원합니다.

또한 다음과 같은 언어에 대한 커뮤니티에서 유지 관리되는 래퍼도 있습니다:

- **Ruby**
- **Swift**
- **Java** (다음 포함):
  - Gradle 플러그인
  - Sass CLI를 감싼 경량 Maven 플러그인. 사용하려는 Sass 버전을 지정하며, CLI 인수는 `<args>` 목록으로 전달됩니다.
  - Dart Sass를 감싼 올인원 Maven 플러그인. 고정된 dart-sass 버전을 번들로 제공합니다. CLI 인수는 Maven 매개변수로 노출됩니다.

## 명령줄

명령줄에서 Sass를 설치하면, `.sass` 및 `.scss` 파일을 `.css` 파일로 컴파일하기 위해 `sass` 실행 파일을 사용할 수 있습니다.

```
sass source/stylesheets/index.scss build/stylesheets/index.css
```

먼저 아래 옵션 중 하나를 사용하여 Sass를 설치한 다음, `sass --version` 명령어를 실행하여 올바르게 설치되었는지 확인하십시오. 설치가 제대로 되었다면 1.77.8 버전이 포함되어 있을 것입니다. 명령줄 인터페이스에 대한 자세한 정보를 얻으려면 `sass --help`를 실행할 수도 있습니다.

모든 설정이 완료되면, Sass를 활용해 보세요. Sass를 처음 사용하는 경우, 빠르게 배울 수 있도록 도와주는 리소스를 준비해 두었습니다.

### 어디에서나 설치 (Standalone)
Windows, Mac 또는 Linux에서 GitHub에서 운영 체제에 맞는 패키지를 다운로드하고 PATH에 추가하여 Sass를 설치할 수 있습니다. 이게 전부입니다—외부 종속성이나 추가로 설치할 항목이 없습니다.

### 어디에서나 설치 (npm)
Node.js를 사용하는 경우, npm을 사용하여 Sass를 설치할 수도 있습니다. 
```
npm install -g sass
```
### Windows에 설치 (Chocolatey)
Windows용 패키지 관리자인 Chocolatey를 사용하는 경우, 다음 명령어를 실행하여 Dart Sass를 설치할 수 있습니다.
```
choco install sass
```

### Mac OS X 또는 Linux에 설치 (Homebrew)
Mac OS X 또는 Linux용 패키지 관리자인 Homebrew를 사용하는 경우, 다음 명령어를 실행하여 Dart Sass를 설치할 수 있습니다.
```
brew install sass/sass/sass
```
