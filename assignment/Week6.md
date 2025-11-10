# SQL_BASIC 6주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_6th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**6주차 과제는 강의 내용을 정리하는 것과 함께, 프로그래머스에서 제공하는 SQL 문제를 직접 풀어보는 실습도 병행합니다.** 강의에서는 **배운 내용을 정리하고 주요 쿼리 예제를 정리**하며, 프로그래머스 문제는 **직접 풀어본 뒤 풀이 과정과 결과, 배운 점을 함께 기록**해주세요. 완성된 과제는 Github에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 

## SQL_BASIC_6th

### 섹션 6. 다량의 자료를 연결 : JOIN 

### 5-1. Intro

### 5-2. JOIN 이해하기

### 5-3. 다양한 JOIN 방법

### 5-4. JOIN 쿼리 작성하기 

### 5-5. JOIN을 처음 공부할 때 헷갈렸던 부분

### 5-6. JOIN 연습문제 1~2번

### 5-6. JOIN 연습문제 3~5번

### 5-7. 정리



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | ✅         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<!-- 여기까진 그대로 둬 주세요-->

<br>

---
<img width="472" height="557" alt="image" src="https://github.com/user-attachments/assets/a1ef6ced-5632-40a8-8ffc-1a4d51a04446" />


# 1️⃣ 개념정리

## 5-2. JOIN 이해하기

~~~
✅ 학습 목표 :
* JOIN에 대한 정의와 필요성에 대해 설명할 수 있다.
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
JOIN이란?
여러 테이블을 공통 값(키)을 기준으로 연결해서
하나의 결과로 만드는 SQL 연산.
BigQuery는 대용량 데이터 분석 환경이므로
JOIN을 효율적으로 쓰는 것이 매우 중요함.
[JOIN의필요성] 
- 관계형 데이터베이스 설계 시 정규화 과정 거침 (중복 최소화, 데이터 구조화)
- user table은 유저 데이터만, order table 은 주문 데이터만(예시) 
- 따라서 데이터를 다양한 table에 저장해 필요할 때 join 해서 사용 
분석 관점에선 미리 join 되어있는것이 좋을 수 있지만 개발 관점에선 분리된게 좋음 

## 5-3. 다양한 JOIN 방법

~~~
✅ 학습 목표 :
* JOIN 방법들의 종류를 설명할 수 있다. 
* 각 JOIN 방법들의 차이점에 대해서 설명할 수 있다. 
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



## 5-4. JOIN 쿼리 작성하기 

~~~
✅ 학습 목표 :
* JOIN을 사용한 문법에 대해 이해하여 적용할 수 있다.
* JOIN 을 활용한 쿼리를 작성할 수 있다. 
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
1) INNER JOIN

양쪽 테이블에 모두 존재하는 값만 가져옴

SELECT *
FROM A
INNER JOIN B
ON A.key = B.key;


교집합만 반환

매칭 안 되면 결과에서 제외

언제 사용?
공통된 데이터만 보고 싶을 때 (예: 주문한 고객만 보기)

2) LEFT JOIN (LEFT OUTER JOIN)

왼쪽 테이블을 기준으로 모두 가져오고, 매칭 안 되는 오른쪽은 NULL

SELECT *
FROM A
LEFT JOIN B
ON A.key = B.key;


A가 기준

A에는 있지만 B에 없는 행도 포함 → B값은 NULL

언제 사용?
전체 고객 목록 중 주문 유무 확인할 때

3) RIGHT JOIN (RIGHT OUTER JOIN)

오른쪽 테이블을 기준으로 모두 가져옴

SELECT *
FROM A
RIGHT JOIN B
ON A.key = B.key;


B가 기준

실무에서 거의 안 씀 → LEFT JOIN으로 방향만 바꿔 해결 가능

언제 사용?
거의 없음 (데이터 파이프라인에서 일부 사용)

4) FULL JOIN (FULL OUTER JOIN)

양쪽 테이블의 모든 행을 가져옴 (매칭 안 되면 NULL)

SELECT *
FROM A
FULL JOIN B
ON A.key = B.key;


합집합

양쪽에 없는 값도 모두 표시

언제 사용?
두 데이터 소스 전체 비교, 통합 리포트 만들 때


## 5-6. JOIN 연습문제 1~5번 

~~~
✅ 학습 목표 :
* 연습문제(3문제 이상) 푼 것들 정리하기
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

<br>
1. 트레이너가 보유한 포켓문들은 얼마나 있는지 알 수 있는 쿼리 작성
SELECT
  t.id AS trainer_id,
  t.kor_name AS trainer_name,
  COUNT(tp.pokemon_id) AS pokemon_cnt
FROM basic.trainer AS t
LEFT JOIN basic.trainer_pokemon AS tp
  ON t.id = tp.trainer_id
  AND tp.status IN ("active", "training")
GROUP BY
  t.id, t.kor_name
ORDER BY
  pokemon_cnt DESC;
2. 각 트레이너가 가진 포켓몬 중 grass타입 포켓몬 수를 계산 
select 
 tp. *, 
 p.type1
from 
 select 
   id 
   trainer_id, 
   pokemon_id, 
  status 
 from trainer_pokemon 
 where 
  status in ("active", "training") 
  ) as tp 
  left join basic.pokemon as p 
  on tp.pokemon_id=p.id 
  where
   type1 ="grass" 
   groupy by
   type1
   order by
   2 desc 
   <img width="888" height="616" alt="image" src="https://github.com/user-attachments/assets/9ae01f15-9d65-4261-8cc6-768ce9b21b9e" />
<img width="1421" height="627" alt="image" src="https://github.com/user-attachments/assets/144a83c8-edbf-45a6-bf7e-23e6771b0898" />

   
<br>

---

# 2️⃣ 확인문제 & 문제 인증

## 프로그래머스 문제 

https://school.programmers.co.kr/learn/courses/30/lessons/164673

> 조건에 부합하는 중고거래 댓글 조회하기 (JOIN)

https://school.programmers.co.kr/learn/courses/30/lessons/144854

> 조건에 맞는 도서와 저자 리스트 출력하기 (JOIN)

<img width="1890" height="911" alt="image" src="https://github.com/user-attachments/assets/6b89f5e1-79a1-414e-b0f9-23c471a94bb8" />
<img width="1887" height="882" alt="image" src="https://github.com/user-attachments/assets/7615cd83-35e7-4128-9902-829f22143d41" />
1. 풀이 과정 
테이블 연결: BOARD와 REPLY 테이블을 BOARD_ID로 JOIN
조건 설정: 게시글 작성일이 2022년 10월인 것만 WHERE로 필터링
결과 형식: 댓글 작성일을 YYYY-MM-DD 형식으로 DATE_FORMAT 지정
정렬: 댓글 작성일, 게시글 제목 순으로 오름차순 정렬

2. 결과 
SELECT A.TITLE, B.BOARD_ID, B.REPLY_ID, B.WRITER_ID, B.CONTENTS,
       DATE_FORMAT(B.CREATED_DATE, '%Y-%m-%d') AS CREATED_DATE
FROM USED_GOODS_BOARD A JOIN USED_GOODS_REPLY B
ON A.BOARD_ID = B.BOARD_ID
WHERE A.CREATED_DATE LIKE '2022-10%'
ORDER BY B.CREATED_DATE, A.TITLE;
3. 배운 점
JOIN으로 데이터 통합하고, LIKE로 날짜 범위를 잡는 법을 익힘
DATE_FORMAT으로 출력 형식을 맞추는 것이 중요함
다중 정렬(ORDER BY) 순서를 정확히 지정해야함 
1. 풀이 과정
테이블 연결: BOOK과 AUTHOR 테이블을 AUTHOR_ID로 JOIN
조건 설정: 도서 카테고리가 **'경제'**인 것만 WHERE로 필터링
   형식: 출판일(PUBLISHED_DATE)을 YYYY-MM-DD 형식으로 DATE_FORMAT 지정
정렬: 출판일 기준으로 오름차순 정렬

2. 결과 
SELECT B.BOOK_ID, A.AUTHOR_NAME,
       DATE_FORMAT(B.PUBLISHED_DATE, '%Y-%m-%d') AS PUBLISHED_DATE
FROM BOOK B JOIN AUTHOR A
ON B.AUTHOR_ID = A.AUTHOR_ID
WHERE B.CATEGORY = '경제'
ORDER BY B.PUBLISHED_DATE ASC;
3. 배운 점 (Key Takeaways)
JOIN으로 데이터 연결하여 도서와 저자 정보를 통합함
WHERE 절로 특정 조건('경제' 카테고리) 데이터만 필터링
DATE_FORMAT으로 출판일 형식을 요구사항에 맞게 처리함
ORDER BY로 단일 기준(출판일) 오름차순 정렬을 적용함


---

# 3️⃣ 참고자료

JOIN 에 대해서 그림으로 쉽게 이해할 수 있는 자료들도 있어서 첨부합니다. 아래의 블로그도 학습할 때 같이 참고해주세요.

1. https://data-marketing-bk.tistory.com/entry/SQL-JOIN-%ED%95%9C-%EB%B0%A9%EC%97%90-%EC%A0%95%EB%A6%AC-%EA%B0%9C%EB%85%90%EB%B6%80%ED%84%B0-%EC%BD%94%EB%93%9C%EA%B9%8C%EC%A7%80-%EC%9D%B4%EA%B2%83%EB%A7%8C-%EB%B3%B4%EC%9E%90



2. https://velog.io/@wijoonwu/JOIN

<br>

### 🎉 수고하셨습니다.
