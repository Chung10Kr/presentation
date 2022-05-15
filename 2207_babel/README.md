# Babel 기본 사용법

# Babel 탄생 배경

자바스크립트 언어는 빠르게 진화하고 있지만 정작 자바스크립트 코드를 실행해주는 환경은

이를 받쳐주지 못하는 경우가 많습니다.

같은 코드도 브라우저에 따라 동작이 다르고 NodeJS의 경우에도 버전별로 지원하는 언어 문법이 다르기 때문에 브라우저만큼은 아니지만 비슷한 문제가 있습니다.

이러한 상황에 개발자는 ES6이상의 최신 문법을 쓰자니 실행 환경에 따라 작동하지 않는 이슈가 생길것이고 모든 환경에서 작동하도록 ES5이하 방식으로 보수적으로 코딩하기도 그렇고

이러한 문제를 해결하기 위해 등장한것이 바로 **Babel** 입니다.

# Babel: Javascript transpiler / Compiler

Babel에 대해서 검색해보면 가장 많이 나오는것이 바로 자바스크립트 컴파일러입니다.

엄밀히 말하면 컴파일은 인간이 작성한 소스코드를 컴퓨터가 이해 할 수 있도록 머신코드로 바꿔주는것을 의미하지만
트랜스파일을 다른 실행 환경에서도 돌아갈 수 있도록 언어를 유지한체 소스 코드의 형태만 바꾸는 과정을 의미합니다.

따라서 Javascript는 Java나 C와 같은 컴파일 언어가 아니고 인터프리터 언어이기 떄문에
컴파일 과정은 필요 없습니다.

엄밀히 말하자면 Babel은 Javascript transpiler이지만 많은 커뮤니티에서 두 용어가 혼용되어 사용되고 있습니다.

# Babel

- Babel은 ES6 이상 코드를 ES5이하의 코드로 변환
- TypeScript 지원
- JSX로 작성된 코드 지원

# Setup

```bash
npm init -y

```

### babel 설치

```bash
npm i -D babel/core babel/cli
# 개발의존성으로 설치하는 이유는 Babel은 애플리케이션 실행 시에 필요한 것이 아니라
# 빌드시에만 필요하기 때문입니다.
# babel/core = Babel을 사용할떄 필요한 패키지
# babel/cli = 터미널에서 커맨트를 입력해서 Babel을 사용할때 필요한 패키지

npx babel .\test01.js
# 실행해보면 아무것도 변경되지 않음 -> 아직 Babel에게 어떻게 코드를 변환할지에 대해서
# 알려주지 않았기 때문
```

### Plugin/Preset설정

```
npm i -D @babel/preset-env
npx babel test01.js --presets=@babel/env

```

### Babel 설정 파일

```
# .babelrc
{
  "presets": ["@babel/env"]
}

```

### NPM 스크립트 설정

```
# package.json

  "scripts": {
    "build": "babel es6 -d dist",
    .
    .
    .
```

# result

```
npm run build
```
