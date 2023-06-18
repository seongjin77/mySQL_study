SELECT * FROM Customers;
-- 의미 : Customers에서 모든 것을 가져오겠다.
-- 이와 같이 주석을 달 수 있습니다.

SELECT CustomerName, ContactName, Country
FROM Customers;
-- 원하는 column(열)만 골라서 보기

SELECT
  CustomerName, 1, 'Hello', NULL
FROM Customers;
-- 테이블의 컬럼이 아닌 값도 선택할 수 있다.
-- 문자열에 ''은 db의 컬럼값이 아니라는 것을 말해줌.

SELECT * FROM OrderDetails 
WHERE Quantity < 5;
-- orderDetails에서 모든 컬럼을 가져오겠다. 단, Quantity가 5미만인 것들만.
-- 문법상 소문자도 상관없음. 하지만 가독성과 sql을 사용했다는 의미로 대문자를 관용적으로 사용.

SELECT * FROM OrderDetails
ORDER BY ProductID ASC, Quantity DESC;
-- ORDER BY 구문을 사용해서 특정 컬럼을 기준으로 데이터를 정렬할 수 있다.
-- 기본값 ASC(생략가능), 역순 DESC

SELECT * FROM Customers
LIMIT 0, 10;
-- LIMIT {가져올 갯수} 또는 LIMIT {건너뛸 갯수}, {가져올 갯수} 를 사용하여, 원하는 위치에서 원하는 만큼만 데이터를 가져올 수 있습니다.

SELECT
  CustomerId AS ID,
  CustomerName AS NAME,
  Address AS ADDR
FROM Customers;
-- 원하는 별명(alias)으로 데이터 가져오기

custom 예

SELECT
  CustomerID AS '아이디',
  CustomerName AS '고객명',
  City AS '도시',
  Country AS '국가'
FROM Customers
WHERE
  City = 'London' OR Country = 'Mexico'
ORDER BY CustomerName
LIMIT 0, 5;

