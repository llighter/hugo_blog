---
title: "Javascript: 함수 정의하기"
date: 2017-04-04T19:00:32+09:00
draft: false
---

# jQuery(javascript)에서는 함수를 사용하는 방법이 크게 두가지가 있다.
아래의 내용은 [MDN-Defining functions][Defining functions]의 내용을 참고한 것이다.

## 1. The function declaration(function statement)

{{< highlight javascript >}}
function name([param[, param[, ... param]]]) {
   statements
}
{{< / highlight >}}

**name**
- 함수의 이름.

**param**
- 함수에 전달될 인자의 이름. 최대 255개 까지 가질 수 있다.

**statements**
- 함수 안에 들어갈 내용들.

## 2. Function expression(function expression)
{{< highlight javascript >}}
function [name]([param[, param[, ... param]]]) {
   statements
}
{{< / highlight >}}
**name**
- 함수의 이름이다. 익명함수로 선언된다면 생략할 수 있다.

**param**
- 함수에 전달될 인자의 이름. 최대 255개 까지 가질 수 있다.

**statements**
- 함수 안에 들어갈 내용들.

#### 2.1 anonymous function expression의 예 (name을 사용하지 않음):

{{< highlight javascript >}}
var myFunction = function() {
    statements
}
{{< /highlight >}}

#### 2.2 named function expression의 예(name을 사용함):

{{< highlight javascript >}}
var myFunction = function namedFunction(){
    statements
}
{{< /highlight >}}

이름을 가지는 `function expression`을 사용하면 코드의 실행중에 에러가 발생하는 경우 `stack trace`에 함수의 이름이 들어가서 에러의 원인을 찾기 쉽다는 장점이 있다.

위의 두 예제에서 볼 수 있듯이 둘다 function 키워드로 시작하지 않는 것을 볼수 있다. 이와 같이, function 키워드로 시작하지 않는 Statements를 `function expression`이라 한다.

만약 내가 사용하는 함수가 단 한번만 쓰인다면, `IIFE` (Immediately Invokable Function Expressions)으로 작성하는 것이 일반적이다.
{{< highlight javascript >}}
(function() {
    statements
})();
{{< /highlight >}}
`IIFT`는 `function expression` 으로 함수가 선언되자 마자 호출이 된다.

[Defining functions]:https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions#The_function_declaration_(function_statement)

