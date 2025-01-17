## 1. 관계형 데이터베이스(RDBMS)와 비관계형 데이터베이스(NoSQL)의 장단점 비교
</br>

**🙋🏻 관계형 데이터베이스(RDBMS)란?**
---
- **RDBMS란 사물을 객체 간의 연관관계로 모델링하여 정해진 규칙대로 데이터를 저장할 수 있는 저장소를 의미합니다.**
- **정해진 스키마에 따라 데이터가 저장되며, 각 테이블은 다른 테이블들과 관계를 맺고 있습니다.**
</br>

🔦 **관계형 데이터 베이스(RDBMS)의 장점**
---
- **데이터의 무결성을 보장하며, 각 데이터는 중복없이 한번만 저장됩니다.**
- **데이터베이스를 추가하기 전에 유효성 검사를 통해 데이터 품질을 향상시킬 수 있습니다.**
- `View`**를 이용한 보안 설정이 가능하기 때문에 허가를 받지 않은 사용자들로부터 데이터의 조회, 변경 및 삭제를 막을 수 있습니다.**
</br>

**⚠️ 관계형 데이터 베이스(RDBMS)의 단점**
---
- **다양한 관계를 맺고 있기 때문에 JOIN작업시 수많은 복잡한 쿼리가 만들어질 수 있습니다.**
- **JOIN 작업 후 복잡한 쿼리가 만들 경우, 수정이 번거롭거나 불가능한 경우가 발생할 수 있습니다.**
- **가변성이 있는 데이터의 경우, 테이블에 저장하는 것이 쉽지 않습니다.**
- **데이터 베이스의 모델링이 개발 전에 완료되어야 합니다.**
</br>

💁🏻‍♂️ **비관계형 데이터베이스(NoSQL)란?**
---
- **NoSQL이란 대량의 분산된 데이터를 저장하고 조회하는데 특화되었으며, 스키마 없이 사용할 수 있는 저장소를 의미합니다.**
- RDBMS에 비해 대용량의 데이터를 저장할 수 있습니다.
</br>

🔦 **비관계형 데이터 베이스(NoSQL)의 장점**
---
- **데이터 모델링이 완료되기 전 테스트 데이터의 조회가 가능합니다.**
- **스키마가 없기 때문에 자유롭게 데이터를 추가할 수 있습니다.**
- **다양한 가변성이 있는 데이터의 저장이 쉽습니다.**
</br>

**⚠️ 비관계형 데이터 베이스(NoSQL)의 단점**
---
- **자유롭게 데이터를 추가하여 데이터 중복이 자주 발생할 수 있습니다.**
- **NoSQL마다 쿼리 언어를 각자 다르게 사용하는 경우가 많아 이식성이 낮습니다.**
- **데이터베이스의 컬렉션이 다양할 경우, 수정할 때에 모든 컬렉션의 데이터를 수정해야 합니다.** 
</br>

## 2. 트랜잭션(transaction)이란 무엇인가요?
</br>


**💁🏻‍♂️ 트랜잭션(transaction)란?**
---

- 트랜잭션이란, 데이터베이스의 상태를 조작(**`SELECT`**, **`UPDATE`**, **`INSERT`**, **`DELETE`**)하기 위해 사용하는 논리적인 작업 단위입니다.

</br>

🔎  **트랜잭션(transaction)의 특징**
---

- **트랜잭션의 특징으로는 원자성, 일관성, 독립성, 지속성이 있습니다.**

- **원자성 (Atomicity) = 트랜잭션의 결과를 DB가 모두 반영하던가, 아니면 전혀 반영되지 않아야 한다는 특징입니다.**

- **일관성 (Consistency)= 트랜잭션의 결과는 항상 일관성이 있어야 한다는 특징입니다.**

- **독립성 (Isolation)= 둘 이상의 트랜잭션이 동시에 실행될 경우, 어떤 하나의 트랜잭션이라도 다른 트랜잭션의 연산에 끼어들 수 없다는 특징입니다.**

- **지속성 (Durability) = 트랜잭션이 성공적으로 완료될 경우, 결과는 영구적으로 반영되어야 한다는 특징입니다.**
</br>

🔎  **트랜잭션(transaction)의 Commit과 RollBack**
---

- **트랜잭션 작업에는 Commit과 RollBack있습니다.**

**Commit**

- **하나의 트랜잭션이 성공적으로 완료하여 DB가 일관성 있는 상태에 있음을 의미합니다.**

**Rollback**

- **만약 하나의 트랜잭션의 처리가 비정상적으로 종료되어 원자성이 깨질때, 트랜잭션을 처음부터 다시 시작하거나, 부분적으로 연산된 결과를 취소시킵니다.**
</br>

## 3. MySQL에서 조인(join)의 역할은 무엇인가요? 다양한 join의 방식에 대해 설명해주세요.
</br>

**💁🏻‍♂️ 조인 (Join)란?**
---

- **조인이란 연관되어 있는 둘 이상의 테이블을 결합하여 하나의 테이블로 만드는 작업입니다.**
- **조인의 작업이 이루어질려면 서로 다른 테이블에서 적어도 하나의 컬럼을 공유하고 있어야 하며, 공유된 칼럼들은 서로 PK 키 또는 FK 키로 사용되어 있어야 합니다.**
</br>

🔎  **조인의 종류**
---

- **MySQL의 조인은 다음과 같이 구분할 수 있습니다.**
- **내부 조인(`INNER JOIN`) = 결합 시 두 테이블에서 JOIN 조건에 만족하는 데이터들만 합쳐주는 조인입니다.**

- **외부 조인(`OUTER JOIN`) = 서로 다른 두 테이블에서 JOIN 조건이 중족하지 않은 데이터라도 합쳐주는 조인입니다.**
- **외부조인은 왼쪽 외부 조인(`LEFT OUTER JOIN`), 오른쪽  외부 조인(`RIGHT OUTER JOIN`), 전체 외부 조인(`FULL OUTER JOIN`)으로 나눌 수 있습니다.**
    - **왼쪽 외부 조인(`LEFT OUTER JOIN`) = 왼쪽 테이블을 기준으로 왼쪽 테이블의 모든 데이터는 포함되고, 오른쪽 테이블의 경우 왼쪽 테이블과 공통된 부분의 값에 대해서만 JOIN작업이 이루어지는 작업입니다.**
    - **오른쪽  외부 조인(`RIGHT OUTER JOIN`) = 오른쪽 테이블을 기준으로 오른쪽 테이블의 모든 데이터는 포함되고, 왼쪽 테이블의 경우 오른쪽 테이블과 공통된 부분의 값에 대해서만 JOIN작업이 이루어지는 작업입니다.**
    - **전체 외부 조인(`FULL OUTER JOIN`) = 왼쪽과 오른쪽 테이블의 모든 값들에 대해서 JOIN 작업이 이루어지는 방식입니다.**

- **자연 조인(`NATURAL JOIN`)= 두 테이블에서 같은 이름을 가진 컬럼들이 모두 동일한 데이터 값을 가질 경우 JOIN 작업이 이루어지는 방식 입니다.**

- **크로스 조인(`CROSS JOIN`) = 서로 다른 두 테이블을 조합할 수 있는 모든 경우를 매칭하여  출력하는 작업니다.**
</br>

## 4. MySQL에서 인덱스(index)란 무엇인가요?
</br>

**💁🏻‍♂️ 인덱스(index)란?**
---
- 인덱스란 책의 목차처럼 MySQL의 데이터를 일관성 있게 정렬하며, 데이터를 빠르게 검색할 수 있도록 하는 자료구조입니다.
- 인덱스의는 MySQL 테이블의 데이터를 **키-값(key-Value)형태로 변경**하며, 테이블 검색 시 인덱스의 키값으로 조회하여 해당 테이블의 특정 컬럼값에 대한 검색 작업이 빠르게 처리됩니다.
</br>

**⚠️ 주의**

- **인덱스는 생성 시 DB의 약 10%정도의 추가 공간이 필요하며, 인덱스 생성시 시간이 오래 걸릴 수 있습니다.**
- 또한 검색(**`SELECT`**) 작업에는 효과적이지만 해당 테이블이 **`INSERT`**, **`UPDATE`**, **`DELETE`**,와 같이 데이터의 변경이 자주 일어난다면,  테이블의 인덱스도 연관되어 작업이 이루어지기 때문에 처리 속도가 느려질 수 있습니다.

**→ 따라서 인덱스는 데이터 변경이 잦은 테이블보다 검색에서 자주 사용하는 테이블에서 주로 사용합니다.**

