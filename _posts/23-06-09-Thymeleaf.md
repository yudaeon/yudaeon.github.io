# Thymeleaf 자주 사용하는 문법

`Thymeleaf` 자주 사용하는 문법

## common

### `th:text`

: 화면에 값을 출력할 때 사용

```java
<span th:text="${nickname}"></span>
```

### `th:if`

:조건문처럼 사용한다. 해당 조건이 만족할 때에만 보여준다.

```java
<div th:if="${error}">
        <p>에러 발생</p>
    </div>
```

### `th:errors`

: 해당 value의 error가 있는 경우 출력한다. 

```java
<ul>
    <li th:errors="*{id}" />
    <li th:errors="*{name}" />
</ul>
```

## form

### `th:action`

: form 태그 사용 시, 해당 경로로 요청을 보낼 때 사용 (url)

### `th:object`

: form submit을 할 때, form의 데이터가 th:object에 설정해준 객체로 받아진다.

### `th:field`

각각 필드들을 매핑을 해주는 역할을 한다. 설정해 준 값으로, th:object에 설정해 준 객체의 내부와 매칭해준다. 

## 중복제거

### `th:fragment`

: `header`, `footer`, `navigation bar`와 같이 모든 페이지에 보여져야 하는 항목인 경우 따로 분리해서 관리한다. 

### **`th:replace`**

`fragment`와 함께 쓰이며, 각 화면에 분리해 놓은 `fragment`를 붙여 넣을 때 사용한다. 

### `th:replace`

태그 전체를 교체해주는 것이다. 

```java
// index.html
<head th:replace="fragments.html :: head"></head>
```

## **`Utility`**

타임리프에서 **`Utili**ty`를 사용할 떄는 `#`을 사용한다. 

```java
th:value="${**#**strings.listJoin(tags, ',')}"
```

## **`strings.listJoin`**

```java
th:value="${#strings.listJoin(tags, ',')}"
문자열 리스트를 ' , ' 를 사용해서 변환해준다
```