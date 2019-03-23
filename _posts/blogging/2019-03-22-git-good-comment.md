---
title: "좋은 커밋 메시지"
categories: 
  - blogging
tags: 
  - jekyll
last_modified_at: 2019-03-23 16:27:00
toc: true
search: true
comments: true
changefreq : daily
priority : 1.0
toc_sticky: true
---

# 들어가며
블로그 시작 후 처음으로 남기는 포스팅이다. 많이 부족하지만 앞으로 실력이 늘겠거니 하고 열심히, 꾸준히 포스팅을 해보려 한다.

# 형상관리란?
소프트웨어 구성 관리(영어: Software Configuration Management) 또는 형상 관리는 소프트웨어의 변경사항을 체계적으로 추적하고 통제하는 것으로, 형상 관리는 일반적인 단순 버전관리 기반의 소프트웨어 운용을 좀 더 포괄적인 학술 분야의 형태로 넓히는 근간을 이야기한다.

> 출처: [위키](https://ko.wikipedia.org/wiki/%EA%B5%AC%EC%84%B1_%EA%B4%80%EB%A6%AC)

# 좋은 커밋 메시지를 작성해야 하는 이유
변경사항을 체계적으로 추적하기 위해서는 우리는 단서를 제공해 주어야 한다. 그 단서는 우리가 남기는 **커밋 메시지 로그**다. 좋은 커밋 메시지는 동료에 대한 배려 및 오류 출처를 찾기 위해서도 반드시 숙지해야 할 사항이다.

# 커밋 메시지
"커밋 메시지를 최대한 자세하게 남겨주세요" 이 말은 의미가 없다. 우리에게 필요한건 좋은 규칙이다.
앞으로 필자가 깃 허브 블로그 프로젝트에 사용 할 커밋 규칙은 아래와 같다.

## 커밋 규칙
~~~
DOC: UI 변경에 따른 메뉴얼 업데이트

고객 요구사항으로 인해 테이블 공통 UI가 변경되어 이미지 파일 교체
~~~
~~~
[커밋 분류코드]: [커밋 제목]

상세내용 작성1
~~~

커밋 분류 코드는 아래와 같이 붙인다.
* NEW: 신규 파일 및 기능 추가
* IMP: 기능 개선
* SCH: 설정 변경
* CLN: 코드 정리 및 리팩토링
* BUG: 버그 픽스
* TST: 테스트
* DOC: 문서작업
* RMV: 삭제

# 마치며
첫 포스팅이라 그런지 내용이 중구난방인듯 싶다. 무튼... 우리가 도구를 활용 하는거지 도구가 우리를 지배하게 해서는 안된다. 개발에 있어서 정해진 답이 없듯이 자신이 어떤 상황이냐에 따라 best way를 찾기 위해 항상 노력 해야겠다.

*ps. gitpro 문서를 읽어보길 강력 추천한다.*

---
# References
* [http://story.haezoom.com/?p=936 : 해줌님 블로그](http://story.haezoom.com/?p=936)
* [https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/](https://item4.github.io/2016-11-01/How-to-Write-a-Git-Commit-Message/)