# 데이터 프레임
#### - **`데이터 프레임`** : 벡터 + 벡터 + 벡터 ...+ 벡터
#### - **`데이터프레임 형태`** :
                a <- c ("홍길동", "유재석", "노홍철") 
                b <- c (3, 6, 8, 9)
                c <- c ("서울", "경기", "부산", "제주")
#### `=> 다양한 벡터가 모여있어 위의 예시와 같이 문자와 숫자를 동시에 사용 가능`
---

#### - **`데이터 프레임 만들기`**
|코드|합치기|문제|관련 코드|
|---|---|---|---|
|name <- c("유재석","노홍철","박명수")
|eng <- c(90,80,60)
|math <- c(40,50,60)|
||`Mid <- data.frame(name,eng,math)`|
|english <- c(90,80,60,70)
|math <- c(50,60,100,20)
|class <- c(1,1,2,2)|
||`df_midterm <- data.frame(english,math,class)`|Q.math의 평균은?|mean(df_midterm`$`math)
|`dim`(iris)|150 5|몇 행, 몇 열로 이루어진 데이터인지 확인
|`str`(iris)|data.frame':	150 obs. of  5 variables:|iris의 `속성 확인`
||$ Sepal.Length: num  5.1 4.9 4.7 4.6 5 5.4 4.6 5 4.4 4.9 ...
||$ Sepal.Width : num  3.5 3 3.2 3.1 3.6 3.9 3.4 3.4 2.9 3.1 ...
||$ Petal.Length: num  1.4 1.4 1.3 1.5 1.4 1.7 1.4 1.5 1.4 1.5 ...
||$ Petal.Width : num  0.2 0.2 0.2 0.2 0.2 0.4 0.3 0.2 0.2 0.1 ...
||$ Species     : Factor w/ 3 levels "setosa","versicolor",..:
---
#### - **`특정 조건의 데이터 프레임 만들기_1`**
|코드|의미|비고|
|---|---|---|
|exam[1,]||1행만 추출
|exam[exam`$`math>=80,]|math가 80점 이상인 행만 추출
|exam[exam`$`class==2 `&` exam`$`math>=80,]|2반이면서 수학점수가 80점 이상
|exam[exam`$`class==1 `:` exam`$`class==2,]|1반이거나 2반
|exam[ ,`c`("class","math")]|class, math 변수 추출|여러가지 변수를 추출시 반드시 `c`로 묶기
|best <- `subset`(변수명,likes == max(love$likes))|likes가 가장 많은 수록곡(변수)만 추출하여 변수 best에 저장|`subset은 전체 데이터에서 조건에 맞는 행들만 추출`|
|df_new1 <- select(df_new,c(1:2))|df_new에서 1~2행 가져오기|
---
#### - **`특정 조건의 데이터 프레임 만들기_2`**
|코드|의미|주의사항|
|---|---|---|
|best <- `subset`(변수명,likes == max(love$likes))|likes가 가장 많은 수록곡(변수)만 추출하여 변수 best에 저장|`subset은 전체 데이터에서 조건에 맞는 행들만 추출`|
|iris_vi %>% filter(sepal.width >=3.0 & petal.width >=2.0) %>% head(3)|sepal.width가 3.0이상이고, petal.width가 2.0이상인 데이터 추출|~와 ~는 같다를 사용할 때는 `==`2개 사용|
