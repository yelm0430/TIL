# **벡터**
## **벡터는 연속된 변수에 사용 가능**
### - 벡터 : 하나(스칼라)또는 여러 개의 값으로 구성된 구조
### - 벡터의 형태 : a <- c ("홍길동", "유재석", "노홍철") => `주의할점 : a <- c ("홍길동", "유재석", "노홍철", 1)과 같이 문자와 숫자가 혼합되어 사용 불가`
### `문자 숫자 출력`
|입력|코드|연산|결과|`주의사항`|
|---|---|---|---|---|
|숫자|age.1 <- 20, age.2 <- 25 | print(age.1 + age.2)| 35
|문자|name.1 <- "john"|print(name.1)|john
|문자 + 숫자|total <- 5050|| total = 5050
||1. cat("합계:",total)
||2.  c("합계:",total)
||- print(age.1 + name.1)||에러| `문자 + 숫자는 에러 발생`
||- a <- c(1,2,3,"4")|| "1" "2" "3" "4"|`숫자가 아닌 문자로 적용됌`
|문자 -> 숫자로 변화|as.numeric(a)||1 2 3 4|
---

### **`벡터 만들기`**
#### - `연속적인 숫자로 이루어진 벡터`

|코드|해석|결과|비고|
|---|---|---|---|
|v3 <- 50:90|50~90까지 연속된수||`연속된 수를 사용할 때는 <- c()를 사용하지 않아도 된다!`
---

#### - 일정한 간격의 숫자로 이루어진 벡터

|코드|해석|결과|비고|
|---|---|---|---|
|v4 <- seq(1,101,3)|[시작,종료,간격]|1,4,7,10...100|
---

#### - **`반복된 숫자로 이루어진 벡터`**

|코드|해석|결과|비고|
|---|---|---|---|
|v5 <- rep(1,times=5)|[1을 5번 반복]|(1)(1)(1)(1)(1)|
|v6 <- rep(1:5,3)|[1,2,3,4,5를 3번 반복]|(1,2,3,4,5) (1,2,3,4,5) (1,2,3,4,5) (1,2,3,4,5) (1,2,3,4,5)
|v7 <- rep(c(1,5,9),)|[1,3,5를 3번 반복]|(1,3,5) (1,3,5) (1,3,5) (1,3,5) (1,3,5)
|v8 <- rep(c(3,6,9),each=6)|[각각을 5번 반복]|(3,3,3,3,3) (6,6,6,6,6) (9,9,9,9,9)|
|v9 <- v2[-5]|v2에서 5번째 원소를 제외한 나머지 원소 추출|
|sample(1:10,5,replace=TRUE)|1 ~10까지 중에서 중복을 허용하여 랜덤으로 5개의 숫자 뽑기||
|sample(1:3,size = 1000,prob=c(0.3,0.6,0.1),replace = TRUE)|1~3까지의 수를 사이즈 1000 중복 허용하여 30% 60% 10%의 확률로 추출|
|table(sample(1:3,size = 1000,prob=c(0.3,0.6,0.1),replace = TRUE))|table로 비율 확인| 1(320)  2(596)   3(84) 
|barplot(table(sample(1:3,size = 1000,prob=c(0.3,0.6,0.1),replace = TRUE)))|barplot 빈도 막대그래프를 추출||
|runif(10,-1,1)|난수 추출 - [개수,최소,최대]|-0.6376104...-0.8312249|
---

#### - **`벡터에서 원소값 확인하기`**

|코드|결과|해석|비고|
|---|---|---|---|
|sales <- c(640,720,680,540)|
|names(sales)<- c('M1','M2','M3','M4')|
|sales[`-c`(2,4)]|640,680|2번쨰 4번째 제외하고 출력
|str5 <- c("Hello!","World","is","good!")|"Hello!" "World" "is" "good!"
---

#### - **`벡터에 저장된 원소값 변경`**

|코드|문제|결과|
|---|---|---|
|play <- c(421,298,254,232,239,368,465)
|names(play) <- c("sun","mon","tue","wed","thu","fri","sat")
||play[c(3,5)] <- c(267,241)로 변경|sun mon tue wed thu fri sat 
|||421 298 267 232 241 368 465|
|df_midterm$report <- c("A","B","A","A")|df_midterm의 3번째 열 추가|english math class report
|||90   50     1      A    
|||100   60    1      B
|||60  100     2      A
|||70   20     2      A
|table(df_midterm$report)|table()report 집계|A(3) B(1) 
|sort(df_midterm$math,decreasing = T)|math() 점수 내림차순|100  60  50  20|
|names(pick) <- c("3rd","7th","32th");pick|
|pick[-2];pick|pick 벡터에서 2열인 '7th'인 값을 제외하고 출력|`항목명을 기준으로 -c("7th)불가`
---

#### - ***`벡터에서 특정 값만 추출하기(중요)`**
|코드|문제|결과|
|---|---|---|
|accident <- c(31,26,42,47,50,54,70,66,43,32,32,22)
|names(accident) <- c("M1","M2","M3","M4","M5","M6","M7","M8","M9","M10","M11","M12")|
|accident_50 <- accident[accident>=50]|사고 건수가 50건이 넘는 달의 통계만 출력|M5 M6 M7 M8 
|||50 54 70 66 
|names(accident[accident>=50])|사고 건수가 50건을 넘는 달의 이름을 출력| "M5" "M6" "M7" "M8"
|length(accident[accident<50])|사고 건수가 50미만인 달을 1년 중 몇 개월인지 출력|8
---
