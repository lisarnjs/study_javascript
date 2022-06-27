June 21, Tuesday

## nullish 병합 연산자 `??`

### 기본 문법

```javascript
a ?? b;
```

- a가 null도 아니고 undefined도 아니면 a
- 그 외의 경우는 b

`??` 없이 `x = a ?? b` 와 동일한 동작을 하느느 코드를 작성하면 다음과 같다.

```javascript
x = a !== null && a !== undefined ? a : b;
```

### example

```javascript
let firstName = null;
let lastName = null;
let nickName = "바이올렛";

// null이나 undefined가 아닌 첫 번째 피연산자
alert(firstName ?? lastName ?? nickName ?? "익명의 사용자"); // 바이올렛
```

### `??` vs `||`

- `||`(OR 연산자)는 첫 번째 truthy 값을 반환
- `??`는 첫 번째 정의된(defined) 값을 반환

**`null`과 `undefined`, `숫자 0`을 구분 지어 다뤄야 할 때 이 차이점이 매우 중요한 역할은 함**

```javascript
let height = 0;

alert(height || 100); // 100
alert(height ?? 100); // 0
```

### 연산자 우선순위

`??`의 연산자 우선순위는 **5**로 꽤 낮다.
따라서 `??`는 `=`와 `?`보다는 먼저, 대부분의 연산자보다는 나중에 평가된다.
그래서 복잡한 표현식 안에서 `??`를 사용해 값을 하나 선택할 땐 괄호를 추가하는 게 좋다.

```javascript
let height = null;
let width = null;

// 괄호를 추가!
let area = (height ?? 100) * (width ?? 50);

alert(area); // 5000
```

**괄호 없이 `??`를 `||`나 `&&`와 함께 사용하는 것은 금지되어 있다.**

> study with [JAVASCRIPT.INFO](https://ko.javascript.info/nullish-coalescing-operator)
