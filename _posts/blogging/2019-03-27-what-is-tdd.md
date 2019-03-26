---
title: "TDD를 도입하자"
categories: 
  - blogging
tags: 
  - TDD
last_modified_at: 2019-03-27 06:55:00
toc: true
search: true
comments: true
changefreq : daily
priority : 1.0
toc_sticky: true
---

---
# 들어가며
운영되고 있는 시스템에 수정 사항이 생기면 정말 난감하다. 간단한 코드 수정에도 부담감이 미친듯이 밀려온다.
나는 나를 믿지 못하기에 믿을 수 있도록 할 수단이 필요했다. TDD... 그 동안 외면해 왔지만 여러 TDD Reference 및 blog를 통해 학습하다보니 그 동안 TDD를 안 해온게 개인 적으로 후회된다. 

# TDD란?
테스트 주도 개발(Test-driven development TDD)은 매우 짧은 개발 사이클을 반복하는 소프트웨어 개발 프로세스 중 하나이다. 개발자는 먼저 요구사항을 검증하는 자동화된 테스트 케이스를 작성한다. 그런 후에, 그 테스트 케이스를 통과하기 위한 최소한의 코드를 생성한다. 마지막으로 작성한 코드를 표준에 맞도록 리팩토링한다. 이 기법을 개발했거나 '재발견' 한 것으로 인정되는 Kent Beck은 2003년에 TDD가 단순한 설계를 장려하고 자신감을 불어넣어준다고 말하였다.

> 출처: [위키](https://ko.wikipedia.org/wiki/%ED%85%8C%EC%8A%A4%ED%8A%B8_%EC%A3%BC%EB%8F%84_%EA%B0%9C%EB%B0%9C)

# TDD를 왜 해야 하는가?
1. 좋은 모델링을 할 수 있다.
-- 테스트 코드는 입력과 출력에 대한 결과이다. 이 과정에서 결합도는 낮고 응집도는 높은 모델링을 작성 할 수 있게한다.
2. 리팩토링에 자신감
-- 좋게 작성된 코드라도 며칠 지나면 레거시 코드다. 특히나 여러명의 개발자 손을 거쳐간 코드라면... 생각만 해도 끔찍하다. 올바르게 작성된 테스트 코드는 리팩토링에 대한 부담감을 줄여준다.
3. 리뷰
-- 테스트 도구와 리뷰도 거치지만 동료와의 리뷰에도 원활한 리뷰 수단이 된다. 이 과정에서 재차 검증이 되며 안정적인 시스템이 만들어 진다.

# TDD 대상
굳이 모든 코드에 대해 테스트 코드를 작성 할 필요는 없다. AWS, Spring, Angular... 이미 너무나도 훌륭한 친구들이다. 우리가 검증하고 보호해야 할 대상은 **도메인**이다. 죽이되든 밥이되든 꼭 지켜야 할 대상이다. 그 외 대상은 다음과 같다. 

1. 중요도가 높은 비즈니스 로직
2. 버그가 발견된 부분
3. 결합이 낮고 논리는 복잡한 부분
4. 새 기능을 추가해야 하는 부분


# TDD시작하기
![TDD3단계 cycle](https://jfiaffe.files.wordpress.com/2014/09/redgreenrefacor.png)

>사람은 한 번에 두 가지 일을 하는 것이 어렵기 때문에 한 번에 한 가지만 집중하기 위하여 TDD 전략을 취한다.-켄트 백
1. RED : “문제를 정의하는 것에 집중한다.”
2. Green : “그 문제를 해결하는데 집중한다.”
3. Refactor : “작성한 코드를 Clean Up하는 것에 집중한다.”

이 3단계를 반복순환 한다.

# 테스트 코드 작성
jest를 install 합니다.
```
npm install --save-dev jest
```
sum.js를 작성합니다.
```
function sum(a, b) {
  return a + b;
}
module.exports = sum;
```
sum.test.js를 작성합니다.
```
const sum = require('./sum');

test('adds 1 + 2 to equal 3', () => {
  expect(sum(1, 2)).toBe(3);
});
```
package.json에 아래코드를 작성합니다.
```
{
  "scripts": {
    "test": "jest"
  }
}
```
실행결과 pass됨을 확인 할 수 있습니다.
```
npm run test

 PASS  ./sum.test.js
  √ adds 1 + 2 to equal 3 (7ms)

Test Suites: 1 passed, 1 total
Tests:       1 passed, 1 total
Snapshots:   0 total
Time:        4.3s
Ran all test suites.
```

# 마치며
TDD는 안정된 시스템을 만들기 위한 서브 수단일 뿐이지 메인이 되서는 안된다. 러닝커브가 있으며 그동안의 코딩 스타일을 바꿔야 하기 때문에 적응하기 쉽지 않을거라 생각한다. 앞으로 TDD를 적절히 활용하여 안정적인 응용 프로그램과 멋진 모델링을 기대하며 테스트 주도 개발을 하자!
<br/><br/>
(*담고싶은 내용은 많은데 포스팅 하는게 익숙치 않은건지... 글 정리를 못 하는건지... 블로거 분들 정말 리스펙 합니다. 원 따봉!*)<br/>


---
# References
* [https://www.youtube.com/watch?v=UttzAcbuk5k&feature=youtu.be](https://www.youtube.com/watch?v=UttzAcbuk5k&feature=youtu.be)
* [https://jestjs.io/docs/en/getting-started](https://jestjs.io/docs/en/getting-started)