## Join

: 둘 이상의 테이블에 걸쳐 있는 데이터가 필요한 경우 사용

- 일반적으로 조인 조건을 포함하는 where 절을 작성해야 함 → 테이블 간의 관계에 대해 잘 알고 있어야 함
- 어떤 테이블을 먼저 읽을지 결정하는 것이 중요 → 처리할 작업량이 달라질 수 있음
- **조인 조건**은 `on`을 이용해서 from절 바로 이후에 작성하는 것을 습관화하도록!

    → mySQL을 제외한 디비를 사용할 때 에러날 확률 없애고, 조인 조건을 빼 먹었을 때도 알아차리기 쉽다!

- `using`을 사용하여 간단하게 조인 조건 작성 가능

    ```sql
    -- join & on 이용
    select employee_id, first_name, salary, department_name
    from employees e inner join departments d
    on e.department_id = d.department_id
    where employee_id = 100;

    -- using 이용
    select employee_id, first_name, salary, department_name
    from employees e inner join departments d
    using (department_id)
    where employee_id = 100;
    ```

- 두 개 이상의 테이블의 조인이 필요할 때 `조인 - 조인 조건 - 조인 - 조인 조건 ...` 으로 작성 가능

    ```sql
    select e.employee_id, e.first_name, j.job_title, e.salary, d.department_name, d.department_id
    from employees e natural join jobs j 
    inner join departments d using(department_id)
    natural join locations l
    where lcase(city)='seattle';
    ```

<br>

## INNER JOIN

: 가장 일반적인 Join의 종류, **교집합**

- N개의 테이블 조인 시 **N-1개의 조인 조건 필요**
- **동등 조인**이라고도 함
- from 절에서 `,`(comma)로 테이블을 연결한 것과 동일

<br>

## NATURAL JOIN

- 두 테이블이 동시에 가지고 있는 컬럼을 사용해서 join 해줌
- `using, on` 사용할 필요 없어짐
- **원하는 조인  조건 외에 같은 컬럼을 가지고 있다면 원하는 결과가 나오지 않을 수 있음!**

<br>

## OUTER JOIN

: 어느 한쪽 테이블에는 해당하는 데이터가 존재하는데 다른 쪽 테이블에는 데이터가 존재하지 않을 경우 그 데이터가 검색되지 않는 문제점을 해결하기 위해 사용

- LEFT OUTER JOIN: 왼쪽 테이블 기준으로 데이터 출력
- RIGHT OUTER JOIN: 오른쪽 테이블 기준으로 데이터 출력
- 해당 테이블 기준으로 join 조건에 일치하지 않아도 데이터 출력

<br>

## SELF JOIN

: 같은 테이블 끼리 Join 하는 것

- alias로 두 테이블을 구분
- 따로 명령어 있는 것은 아님!

<br>

## non eq join

: 동등 조인이 아닌 조인!

```sql
select e.employee_id, e.first_name, e.salary, s.grade
from employees e join salgrades s
on e.salary >= s.losal
and e.salary < s.hisal;
```

- 임금의 범위로 임금 등급을 나누고 있음