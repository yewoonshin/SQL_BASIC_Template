## 문제 1

> **🧚Q. 포켓몬 마스터 승화는 포켓몬 데이터 조회하는 SQL문에 재미를 느껴서 혼자서 데이터를 조회하는 쿼리문을 짰습니다. 하지만 세 가지의 오류로 다음 코드가 실행이 안된다고 하는데, 각 오류의 위치와 이유를 설명하고, 올바른 쿼리문으로 수정해보세요.**

~~~sql
# 승화의 SQL Query문 
SELECT name AS '포켓몬 이름', ID;
WHERE type = 'Electric';
FROM pokemon;
~~~



~~~sql
# 정답 
SELECT name AS 포켓몬_이름, id
FROM pokemon
WHERE type = 'Electric';

# 총 3가지의 오류가 존재한다. 
# 1. SELECT name AS '포켓몬 이름', ID; : ';' 기호가 SELECT 안에 존재한다. 
# 2. WEHRE가 FROM 보다 앞에 나온다. 구문 순서가 위반된다. (SQL 기본순서 SELECT -> FROM -> WHERE)
# 3. AS '포켓몬 이름' : 별칭(alias)은 따옴표(" ")나 없음이 표준이다. (DB에 따라 다르긴하다.)

~~~



## 문제 2

> **🧚Q. 앞서 SQL Query의 오류를 해결한 승화는 기분 좋게 이번에는 포켓몬 데이터에서 타입별 평균 공격력이 60 이상인 타입만 조회하려는 쿼리를 작성하려고 했습니다. 하지만 이번에도 실수를 하여 쿼리문이 실행되지 않거나 잘못된 결과가 나오고 있는데, 쿼리에서 잘못된 부분이 무엇인지 설명하고, 올바르게 수정한 쿼리를 작성해보세요.**

~~~sql
SELECT type, AVG(attack) AS avg_attack
FROM pokemon
WHERE AVG(attack) >= 60
GROUP BY type;
~~~



~~~sql
# 정답 
SELECT type, AVG(attack) AS avg_attack
FROM pokemon
GROUP BY type
HAVING AVG(attack) >= 60;

# 총 2가지의 오류가 존재한다.
# 1. SQL 구문 순서
# 2. 집계함수에 WHERE를 사용함. 
~~~
