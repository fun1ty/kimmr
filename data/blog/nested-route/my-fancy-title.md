---
title: My fancy title
date: '2021-01-31'
tags: ['hello']
draft: true
summary:
images: []
---

Draft post which should not display

A sample post with markdown.

## Inline Highlighting

Sample of inline highlighting `sum = parseInt(num1) + parseInt(num2)`

## Code Blocks

Some Javascript code

```javascript
var num1, num2, sum
num1 = prompt('Enter first number')
num2 = prompt('Enter second number')
sum = parseInt(num1) + parseInt(num2) // "+" means "add"
alert('Sum = ' + sum) // "+" means combine into a string
```

Some Python code 🐍

```python
def fib():
    a, b = 0, 1
    while True:            # First iteration:
        yield a            # yield 0 to start with and then
        a, b = b, a + b    # a will now be 1, and b will also be 1, (0 + 1)

for index, fibonacci_number in zip(range(10), fib()):
     print('{i:3}: {f:3}'.format(i=index, f=fibonacci_number))
```

프로젝트페이지

```
const projectsData = [
  {
    title: 'A Search Engine',
    description: `What if you could look up any information in the world? Webpages, images, videos
    and more. Google has many features to help you find exactly what you're looking
    for.`,
    imgSrc: '/static/images/google.png',
    href: 'https://www.google.com',
  },
  {
    title: 'The Time Machine',
    description: `Imagine being able to travel back in time or to the future. Simple turn the knob
    to the desired date and press "Go". No more worrying about lost keys or
    forgotten headphones with this simple yet affordable solution.`,
    imgSrc: '/static/images/time-machine.jpg',
    href: '/blog/the-time-machine',
  },
]

export default projectsData

```

---

title: Hook이란? | React
date: '2023-09-24'
tags: ['[포스코x코딩온] 웹개발자 풀스택 과정', 'React']
draft: false
summary: Hook으로 class없이 React의 기능을 사용할 수 있다.
images: [src: '/static/images/주차하카.svg']

---

<h2>Intro</h2>
리액트를 배운지 일주일이 지났다. 자바스크립트를 대충 아는 상태에서 리액트를 접하니 쉽지는 않다. 나름의
복습을 하고는 있느나, 정처기 시험이 코앞이라(10/7) 시간을 많이 할애하지 못하는 점이 아쉽다. 그러나 글을
통한 체화과정은 놓칠수 없기에 새로 배운 리액트 Hook을 포스팅하고자 한다.{' '}

<h3>Hook이란?</h3>
공식문서와 수업때 배운 내용을 종합해 보자면, Hook은 class형 컴포넌트에서 사용할 수 있던 상태관리와 생명주기
기능을 함수형 컴포넌트에서도 연동할 수 있게끔 만들어주는 기능이다. 왜 class형 컴포넌트를 계속 사용하지
않고 Hook이라는 기능을 도입하였을까? 공식문서의 [Hook소개](https://ko.legacy.reactjs.org/docs/hooks-intro.html#motivation)
라는 부분을 보면 class 컴포넌트에서 사용하는 this 키워드는 자바스크립트의 this이며, 이것은 다른 언어와는
다르게 동작하기에 사용자들에게 많은 혼란을 야기한듯 하다. 또한 class의 사용을 위해서는 이벤트 핸들러의
등록을 정확히 알아야 했고 이러한 여러가지 문제점 때문에 사용자들은 class 이해의 어려움을 겪었다고 한다.
때문에 Hook이 도입되었다.{' '}

<h3>Hook의 종류</h3>
학습한 내용을 토대로 기본 Hook은 아래와 같다. (공식문서에는 더 많은 종류가 있다.)

- useState
- useEffect

추가 Hook은 아래와 같다.

- useReducer
- useCallback
- useMemo
- useRef

<h3>useState</h3>

상태 유지값과 그 값을 갱신한다.
최초 랜더링 시, status에는 useState("초기값")이 전달되어 화면에 출력된다. 이후, 이벤트 동작에 따라 setStatus에 전달된 값이 status에 전달되어 리랜더링시에 반영된다.

```
const [status, setStatus] = useState("초기값");
```

<h3>Hook의 사용법</h3>

<h3>As a result...</h3>

<hr />
출처 <br />
https://ko.legacy.reactjs.org/docs/hooks-overview.html
