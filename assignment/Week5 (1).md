# SQL_BASIC 5주차 정규 과제 

📌SQL_BASIC 정규과제는 매주 정해진 분량의 `초보자를 위한 BigQuery(SQL) 입문` 강의를 듣고 간단한 문제를 풀면서 학습하는 것입니다. 이번주는 아래의 **SQL_Basic_5th_TIL**에 나열된 분량을 수강하고 `학습 목표`에 맞게 공부하시면 됩니다.

**5주차 과제는 문제 풀이를 중심으로**, 강의에서 제시된 예제 문제 중 **3 문제 이상을 선택하여 직접 풀어본 뒤**, 강의 영상의 풀이와 비교해 **틀린 부분, 맞은 부분, 새롭게 배운 개념**을 구체적으로 정리해주세요. (적어도 4문제는 정리해야 합니다.) 완성된 과제는 Gihub에 업로드하고, 링크를 스프레드시트 'SQL' 시트에 입력해 제출해주세요.

**(수행 인증샷은 필수입니다.)** 




## SQL_BASIC_5th

### 섹션 5. 데이터 탐색 - 변환

### 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

### 4-5. 시간 데이터 연습문제 1~2번

### 4-5. 시간 데이터 연습문제 3~5번

### 4-6. 조건문 (CASE WHEN, IF)

### 4-7. 조건문 연습 문제

### 4-8. 정리

### 4-9. BigQuery 공식 문서 확인하는 법

(강의에서 연습문제가 많아서 따로 프로그래머스 문제 과제는 없습니다.)



## 🏁 강의 수강 (Study Schedule)

| 주차  | 공부 범위              | 완료 여부 |
| ----- | ---------------------- | --------- |
| 1주차 | 섹션 **1-1** ~ **2-2** | ✅         |
| 2주차 | 섹션 **2-3** ~ **2-5** | ✅         |
| 3주차 | 섹션 **2-6** ~ **3-3** | ✅         |
| 4주차 | 섹션 **3-4** ~ **4-4** | ✅         |
| 5주차 | 섹션 **4-4** ~ **4-9** | ✅         |
| 6주차 | 섹션 **5-1** ~ **5-7** | 🍽️         |
| 7주차 | 섹션 **6-1** ~ **6-6** | 🍽️         |

<br>



<!-- 여기까진 그대로 둬 주세요-->

---

# 4-4. 날짜 및 시간 데이터 이해하기(2) (EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME)

~~~
✅ 학습 목표 :
* 날짜 및 시간 데이터에 대해서 더 자세히 설명할 수 있다. 
* CURRENT_TIME, EXTRACT, DATETIME_TRUNC, PARSE_DATETIME, FROMAT_DATETIME 을 설명할 수 있다. 
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
extract: 특정 부분만 추출하고 싶은 경우 (예: extract date from date time "2025-11-03 14:00:00") as date
dayofweek: 요일만 추출 가능 월-1, 화-2, .... 일-7 
DATETIME_TRUNC: date와 hour만 남기고 싶은 경우의 시간 자르기 
PARSE_DATETIME : 문자열로 저장된 datetime을 datetime타입으로 바꾸고싶은 경우 
  문자열을 date 타입에 맞게 파싱됨 
  format elements 문서를 확인하면 %Y등이 어떤 문제인지 확인 가능 
  LAST_DAY: 마지막날을 알고싶은 경우 자동으로 월의 마지막 값을 계산해 특정 연산 
  두 DATETIME의 차이를 알고 싶은 경우 DATETIME_DIFF (며칠차이인가?) 
  두 MONTH 차이를 알고자 하면 MONTH_DIFF 
날짜 및 시간 데이터 타입 
-DATE
-DATETIME: DATE+TIME



# 4-6. 조건문(CASE WHEN, IF)

~~~
✅ 학습 목표 :
* 조건문 함수의 기능을 이해하고, 설명할 수 있다. 
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->
조건문 함수가 필요한 이유: 특정 카테고리를 하나로 합치는 전처리 필요 
 왜냐하면, 저장하는 쪽과 분석하는 쪽이 나뉨. 
  -> 분석할 때 필요한 부분에서 조건 설정해서 변경하는 것이 더 유용함. 
1) CASE WHEN
   -여러 조건이 있을 경우 유용 
   - 문법
     select
       case
         when 조건1 then (조건1이 참일 경우 결과)
         when 조건2 then (조건2가 참일 경우 결과)
         else 그 외 조건일 경우 결과
       end as 새로운 컬럼_이름
   ** 순서 중요!!
     - 조건1, 조건2에 둘다 해당하면 앞선 순서 따름
     - 문자열 함수(특정단어 추출)에서 이슈 발생
  2) IF
     -단일 조건일 경우 유용
     -문법 IF(조건문, true일때 값, false일떄 값) as 새로운 컬럼 이름 
 # 4-5. 시간 데이터 연습문제 & 4-7. 조건문 연습 문제


 # 4-5. 시간 데이터 연습문제 & 4-7. 조건문 연습 문제

~~~
✅ 학습 목표 :
* 4-5, 4-7 각각에서 두 문제 이상 (최소 4문제) 푼 내용 정리하기
~~~

<!-- 새롭게 배운 내용을 자유롭게 정리해주세요.-->



<br>

<br>

---

# 확인문제

## 문제 1

> **🧚Q. 광윤이는 사용자 로그 데이터에서, 2021년에 접속한 사용자 수를  집계하려고 했습니다. 그는 여러 SQL 쿼리들을 실행해봤지만, 그 중 일부는 문법적으로 잘못되어 실행되지 않았습니다. 다음 보기 중 틀린 쿼리를 모두 골라보세요 (복수 선택 가능)**

~~~sql
1. SELECT COUNT(*)  
   FROM user_log  
   WHERE EXTRACT(YEAR FROM login_date) = 2021;

2. SELECT EXTRACT(YEAR FROM login_date), COUNT(*)  
   FROM user_log  
   GROUP BY EXTRACT(YEAR FROM login_date);

3. SELECT COUNT(*)  
   FROM user_log  
   WHERE login_date = '2021';

4. SELECT COUNT(*)  
   FROM user_log  
   WHERE login_date BETWEEN '2021-01-01' AND '2021-12-31';
~~~

<!-- 틀린쿼리에 대한 오류의 원인도 같이 작성해주세요. 문제에서 제공된 login_data 컬럼은 DATE type의 데이터를 가지고 있다고 가정하시면 됩니다. -->

~~~
여기에 답을 작성해주세요!
3번: login_date가 date 타입인데 '2021'은 문자열 타입
~~~



## 문제 2

> **🧚Q. 혜성이는 포켓몬 타입에 따라 설명을 부여하는 쿼리를 작성했습니다. type 1 컬럼의 값에 따라 조건을 분기했으며, 다음 SQL 쿼리를 실행했습니다.**

~~~sql
SELECT name,
       CASE 
         WHEN type1 = 'Fire' THEN 'Hot'
         WHEN type1 = 'Water' THEN 'Cool'
         ELSE 'Normal'
       END AS type_description
FROM pokemon;
~~~

> **다음 중 type_description의 결과가 'Normal'로 출력될 포켓몬은?**

| **name**   | **type1** |
| ---------- | --------- |
| Pikachu    | Electric  |
| Charmander | Fire      |
| Squirtle   | Water     |
| Bulbasaur  | Grass     |

<!-- 근거와 함께 답을 작성해주세요 -->

~~~
여기에 답을 작성해주세요!
pikachu, Buldasaur
case문에서 지정한 조건(fire, water)에 해당하지 않는 type1값 (electric, grass)는 else 'normal'로 분류되므로 type_description결과가 'normal'로 출력됨

~~~



<br>

### 🎉 수고하셨습니다.
