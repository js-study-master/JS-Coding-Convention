# JS-Coding-Convention

> 스터디의 코딩 컨벤션은 기본적으로 Airbnb사의 코딩 컨벤션을 베이스로 합니다. <br>
  Link: [airbnb/JavaScript Style Guide](https://github.com/airbnb/javascript)

> 이 문서는 효율적이고 간결한 코드 스타일을 위해 필수적인 부분만을 추려놓았습니다.

## 목차
  1. [주석](#주석)
  2. [공백](#공백)
  3. [네이밍 규칙](#네이밍-규칙)
  4. [속성](#속성)
  5. [비교 연산자](#비교-연산자)


## 주석

1.1 multi-line 주석
-  `/** ... */` 을 사용하세요.
    ```javascript
    // 나쁜 예
    // make() returns a new element
    // based on the passed in tag name
    //
    // @param {String} tag
    // @return {Element} element
    function make(tag) {

      // ...

      return element;
    }

    // 좋은 예
    /**
     * make() returns a new element
     * based on the passed-in tag name
     */
    function make(tag) {

      // ...

      return element;
    }
    ```
1.2 single-line 주석
- `//` 을 사용하세요. 주석 위에는 한줄을 띄워주세요 (블록의 첫 문장인 경우는 예외)

    ```javascript
    // 나쁜 예
    const active = true;  // is current tab

    // 좋은 예
    // is current tab
    const active = true;

    // 나쁜 예
    function getType() {
      console.log('fetching type...');
      // set the default type to 'no type'
      const type = this.type || 'no type';

      return type;
    }

    // 좋은 예
    function getType() {
      console.log('fetching type...');

      // set the default type to 'no type'
      const type = this.type || 'no type';

      return type;
    }

    // 좋은 예
    function getType() {
      // set the default type to 'no type'
      const type = this.type || 'no type';

      return type;
    }
    ```
1.3 모든 주석은 한 칸의 공백(Whitespace)으로 시작하세요.
  ```javascript
  // 나쁜 예
  //is current tab
  const active = true;

  // 좋은 예
  // is current tab
  const active = true;

  // 나쁜 예
  /**
   *make() returns a new element
  *based on the passed-in tag name
  */
  function make(tag) {

    // ...

    return element;
  }

  // 좋은 예
  /**
   * make() returns a new element
   * based on the passed-in tag name
   */
  function make(tag) {

    // ...

    return element;
  }
  ```
## 공백
2.1 탭키를 2 spaces로 바꿔주세요. (Default로 4가 설정되어있음)

2.2 중괄호 앞에는 공백을 하나 넣어주세요.
  ```javascript
  // 나쁜 예
  function test(){
    console.log('test');
  }

  // 좋은 예
  function test() {
    console.log('test');
  }

  // 나쁜 예
  dog.set('attr',{
    age: '1 year',
    breed: 'Bernese Mountain Dog',
  });

  // 좋은 예
  dog.set('attr', {
    age: '1 year',
    breed: 'Bernese Mountain Dog',
  });
  ```

2.3 제어문 (`if`, `while` etc.)에서 여는 괄호전에 1칸의 공백을 두세요. 함수의 호출 및 선언에서 argument와 함수 이름 사이에는 공백을 넣지 마세요.
```javascript
  // 나쁜 예
  if(isJedi) {
    fight ();
  }

  // 좋은 예
  if (isJedi) {
    fight();
  }

  // 나쁜 예
  function fight () {
    console.log ('Swooosh!');
  }

  // 좋은 예
  function fight() {
    console.log('Swooosh!');
  }
```

2.4 연산자는 모두 양 옆에 공백을 두세요.
```javascript
  // bad
  const x=y+5;

  // good
  const x = y + 5;
```
2.5 블록 다음과 다음 문 시작 전엔 한 줄을 띄우세요.
```javascript
  // bad
  if (foo) {
    return bar;
  }
  return baz;

  // good
  if (foo) {
    return bar;
  }

  return baz;

  // bad
  const obj = {
    foo() {
    },
    bar() {
    },
  };
  return obj;

  // good
  const obj = {
    foo() {
    },

    bar() {
    },
  };

  return obj;

  // bad
  const arr = [
    function foo() {
    },
    function bar() {
    },
  ];
  return arr;

  // good
  const arr = [
    function foo() {
    },

    function bar() {
    },
  ];

  return arr;
```
## 네이밍 규칙
3.1 한 글자 이름은 쓰지마십시오.
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
3.2 오브젝트, 함수, 인스턴스의 이름을 지을 땐, camelCase를 사용하세요.
```javascript
  // 나쁜 예
  const OBJEcttsssss = {};      // PascalCase
  const this_is_my_object = {}; // snake_case
  function c() {}               // 한 글자

  // 좋은 예
  const thisIsMyObject = {};
  function thisIsMyFunction() {}
```

3.3 PascalCase는 생성자나 클래스의 이름을 지을 때만 사용하세요.
```javascript
  // 나쁜 예
  function user(options) {
    this.name = options.name;
  }

  const 나쁜 예 = new user({
    name: 'nope',
  });

  // 좋은 예
  class User {
    constructor(options) {
      this.name = options.name;
    }
  }

  const 좋은 예 = new User({
    name: 'yup',
  });
```
3.4 두문자어는 항상 대문자로 쓰세요.
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

  // 가장 좋은 예
  import TextMessageContainer from './containers/TextMessageContainer';
```
## 속성
4.1 속성에 접근할 땐, 점 표기법을 사용하세요.
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
4.2 괄호 표기법은 변수로 접근할 때만 쓰세요.
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
## 비교 연산자

5.1 `==`와 `!=` 대신에 `===`와 `!==`를 사용하세요.

5.2 if 문과 같은 조건문은 `ToBoolean` 추상 메서드로 강제 변환을 사용하여 식을 계산하고 항상 다음과 같은 간단한 규칙을 따릅니다.
  * **오브젝트**는 **true**입니다.
  * **Undefined**는 **false**입니다.
  * **Null**은 **false**입니다.
  * **숫자**는 **+0**, **-0**, 이나 **NaN**이면 **false**이고, 나머지는 **true**입니다.
  * **문자열**은 빈 문자열 `''`이면 **false**이고, 나머지는 **true**입니다.
  > 참고! [그림으로 보는 비교](https://dorey.github.io/JavaScript-Equality-Table/)

5.3 연산자를 섞어 사용할 때는, 연산자를 괄호로 묶으십시오. 표준 연산자 (`+`, `-`, `*`, `&` `/`)는 예외입니다.
```javascript
  // 나쁜 예
  const foo = a && b < 0 || c > 0 || d + 1 === 0;

  // 좋은 예
  const foo = (a && b < 0) || c > 0 || (d + 1 === 0);

  // 좋은 예
  const bar = a + b / c * d;
```