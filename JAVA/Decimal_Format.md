## 소수점 자리 수 표현

DecimalFormat 클래스 이용

```java
Double d1 = 1.1234567;
DecimalFormat form = new DecimalFormat("#.##");
System.out.pritnln(form.format(d1)); // 1.12 출력
```