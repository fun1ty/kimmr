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
title: 사용자 인증 방법 및 암호화 | node.js
date: '2023-08-18'
tags:
  [
    '[포스코x코딩온] 웹개발자 풀스택 과정',
    '7주차',
    'cookie',
    'seession',
    'node.js',
    'mysql',
    'JWT',
    'Sequelize',
  ]
draft: false
summary: cookie와 session, jwt를 이용한 사용자인증 및 비밀번호 암호화를 배움.
images: ['/static/images/profile.png']
---

<h3>Intro</h3>
해외spa 패션사이트를 들어가면 맞춤형 광고를 위한 사용자 쿠키저장을 허용할 것인가라는 팝업창이 뜨면서
필수적 쿠키와 광고를 위한 쿠키 저장 등이 뜬다. 몇년전에는 안떴던거 같은데..정책이 바뀐것인지 아니면 내가
몰랐던 것인지는 모르겠지만 아무리 체크를 해도 몇일이 지나면 다시 떠서 여간 번거러운게 아니였는데 이번에
왜그런지 알게되었다. 이 포스팅에서는 cookie와 session, 그리고 jwt 인증방식을 소개하고 비밀번호 암호화하는
순으로 이어진다.

<h3>Cookie</h3>
