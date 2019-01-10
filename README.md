# JS-Coding-Convention

## Table of Contents

  3. [네이밍 규칙](#네이밍-규칙)
  4. [속성](#속성)
  5. [비교 연산자와 동치](#비교-연산자와-동치)
## 네이밍 규칙
- 한 글자 이름은 쓰지마십시오.
```javascript
    // 나쁜 예
    function q() {
      // ...
    }

    // 좋은 예
    function query() {
      // ...
    }
```
- 오브젝트, 함수, 인스턴스의 이름을 지을 땐, camelCase를 사용하세요.
```javascript
  // 나쁜 예
  const OBJEcttsssss = {};      // PascalCase
  const this_is_my_object = {}; // snake_case
  function c() {}               // 한 글자

  // 좋은 예
  const thisIsMyObject = {};
  function thisIsMyFunction() {}
```

- PascalCase는 생성자나 클래스의 이름을 지을 때만 사용하세요.
```javascript
  // 나쁜 예
  function user(options) {
    this.name = options.name;
  }

  const bad = new user({
    name: 'nope',
  });

  // 좋은 예
  class User {
    constructor(options) {
      this.name = options.name;
    }
  }

  const good = new User({
    name: 'yup',
  });
```
- 두문자어는 항상 대문자로 쓰세요.
```javascript
  // 나쁜 예
  import SmsContainer from './containers/SmsContainer';

  // 나쁜 예
  const HttpRequests = [
    // ...
  ];

  // 좋은 예
  import SMSContainer from './containers/SMSContainer';

  // 좋은 예
  const HTTPRequests = [
    // ...
  ];

  // best
  import TextMessageContainer from './containers/TextMessageContainer';
```

## 속성
- 속성에 접근할 땐, 점 표기법을 사용하세요.
```javascript
  const luke = {
    jedi: true,
    age: 28,
  };

  // 나쁜 예
  const isJedi = luke['jedi'];

  // 좋은 예
  const isJedi = luke.jedi;
```
- 괄호 표기법은 변수로 접근할 때만 쓰세요.
```javascript
  const luke = {
    jedi: true,
    age: 28,
  };

  function getProp(prop) {
    return luke[prop];
  }

  const isJedi = getProp('jedi');
```

## 비교 연산자와 동치

- `==`와 `!=` 대신에 `===`와 `!==`를 사용하세요.

- if 문과 같은 조건문은 `ToBoolean` 추상 메서드로 강제 변환을 사용하여 식을 계산하고 항상 다음과 같은 간단한 규칙을 따릅니다.
  * **오브젝트**는 **true**입니다.
  * **Undefined**는 **false**입니다.
  * **Null**은 **false**입니다.
  * **숫자**는 **+0**, **-0**, 이나 **NaN**이면 **false**이고, 나머지는 **true**입니다.
  * **문자열**은 빈 문자열 `''`이면 **false**이고, 나머지는 **true**입니다.
  > 참고! [그림으로 보는 비교](https://dorey.github.io/JavaScript-Equality-Table/)
- 연산자를 섞어 사용할 때는, 연산자를 괄호로 묶으십시오. 표준 연산자 (`+`, `-`, `*`, `&` `/`)는 예외입니다.
```javascript
  // 나쁜 예
  const foo = a && b < 0 || c > 0 || d + 1 === 0;

  // 좋은 예
  const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

  // 좋은 예
  const bar = a + b / c * d;
```