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

## p20230811 작성중

title: Sequelize와 ORM | node.js
date: '2023-08-10'
tags: ['[포스코x코딩온] 웹개발자 풀스택 과정', '6주차', 'node.js', 'mysql']
draft: false
summary: sequelize를 이용한 ORM

---

<strong>
  <h3>Intro</h3>
</strong>
기존 포스팅을 보면, mysql에서 테이블을 sql구문으로 손수 생성하고 controller에서 sql을 직접 작성하여 DB상태를
변경하였다. 이 부분에서 객체 모델과 관계형 모델 간에 불일치가 존재하며 Sequelize를 이용한 ORM으로 이것을
해결하는 것을 배웠다. <br /> 이 포스팅은 ORM이란 무엇인지와 sequelize에 대해서 설명하고 이 개념을 이용해
만든 CRUD 기능이 있는 회원가입, 로그인, 프로필페이지가 있는 간단한 예제의 구현코드를 설명한다.

<strong>
  <h3>ORM?</h3>
</strong>
> Object Relational Mapping, 객체-관계 매핑

한마디로 관계형 데이터베이스와 객체 지향 프로그래밍 언어 간의 호환되지 않는 데이터를 자동으로 매핑(연결)해주는 프로그래밍 기법이다. 좀 더 적나라하게(?) 설명하자면 node.js의 controller에서 sql구문을 이용해 RDBMS의 데이터를 연결해주던 것을 Sequelize 라이브러리를 통해 쉽게 연결할수 있다는 것이다. 데이터 매핑구조를 객체지향형으로 통일시키기 때문에 한층 더 oop적 구조에 가까워진다. <br/>
사실 처음 보았을때는 환경변수 설정이나 sequelize 문법등이 생소하여 진입장벽이 높게 느껴졌으나 막상 사용해보니 model에서 콜백함수로 결과값을 반환해주기 위해 RDBMS 구문으로 한번 더 작성하는 대신 model에서는 DB만 정의하고 controller에서 한번에 처리하니 훨씬 더 효율적인 방법이라고 느꼈다.

<strong>
  <h3>As a result...</h3>
</strong>
<hr />
출처 <br />
https://hanamon.kr/orm%EC%9D%B4%EB%9E%80-nodejs-lib-sequelize-%EC%86%8C%EA%B0%9C/ <br />
http://www.incodom.kr/ORM <br />
https://gmlwjd9405.github.io/2019/02/01/orm.html <br />
https://munak.tistory.com/entry/DBORMObject-Relational-Mapping%EC%9D%B4%EB%9E%80
