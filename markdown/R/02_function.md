# 함수

### **`산수 함수`**
- 예시 코드 : total <- c(60, 95, 83, 76, 90, 80, 85, 91, 82, 70)

|함수|코드|결과|비고
|---|---|---|---|
|합계|sum(total)|812|
|중앙값|mean(total)|81.2
|중간값|median(total)|82.5
|최소값|min(total)|60
|최대값|max(total)|95
|최소값,최대값|range(total)|60 95
|분산|var(total)|109.5111|
|표준편차|sd(total)|10.46476|표준편차가 작을수록 평균에 모여있다는 의미
|요약|summary(total)| Min.   1st Qu.    Median      Mean 3rd Qu.      Max. 
|||60.00     77.00     82.50     81.20     88.75     95.00 
||`summerise()`||데이터 프레임에서 사용
||||group_by() 함수와 함께 사용
|그래프|plot(total)||
|집계|table(total)||겹치는 항목의 개수를 구해줌
|오름차순|sort(total)|
|내림차순|sort(total,decreasing=True)|
|최대값을 갖는 원소 인덱스를 추출|which.max(DB)|인덱스 번호가 결과값
|최소값을 갖는 원소 인덱스를 추출|which.min(DB)|인덱스 번호가 결과값
|특정 값보다 큰  원소 추출|total[ total > 80 ]|95, 83,90, 80, 85, 91, 82|
---
### `자료 구조 생성/확인/변환에 대한 함수`
|함수|의미|
|---|---|
|matrix()|매트릭스 자료구조 생성|
|data.frame()|데이터프레임 자료구조 생성
|cbind()|열 방향으로 데이터셋을 결합
|rbind()|행 방향으로 데이터셋을 결합
|class()|데이터셋의 자료구조 확인
|is.matrix()|자료구조가 매트릭스인지 확인
|is.data.frame()|자료구조가 데이터프레임인지 확인
|as.matrix()|데이터프레임을 매트릭스로 변환(단 모든 값들의 자료형은 동일해야함)
|t()|매트릭스의 행과 열의 방향 변환
---
### `데이터셋의 기본 정보를 알아보는 함수`
|함수|의미|
|---|---|
|dim()|데이터셋의 행과 열의 개수
|nrow()|데이터셋의 행으 ㅣ개수
|ncol()|데이터셋의 열의 개수
|rownames()|데이터셋의 행 이름 출력
|colnames()|데이터셋의 열 이름 출력
|head()|데이터셋의 앞쪽 몇 행만 출력
|tail()|데이터셋의 뒷쪽 몇 행만 출력
|str()|데이터셋에 대한 요약 정보 출력
|table()|값으 ㅣ종류별 빈도 출력
---
### `데이터셋 분석을 위해 자주 사용하는 함수`
|함수|의미|
|---|---|
|colSums()|데이터셋의 열별 합계
|rowSums()|데이터셋의 행별 합계
|colMeans()|데이터셋의 열별 평균
|rowMeans()|데이터셋의 행별 평균
|subset()|데이터셋에서 조건에 맞는 행 추출
---
### `조건문`
|함수|코드|예시|의미|주의할점|
|---|---|---|---|---|
|if|`ifelse`(조건, 조건이 참일 때, 조건이 거짓일 때)|ifelse(score>=90,"A학점","재시험")|score가 90이상이면 A학점, 아니면 재시험|
||`if`(score>=30){|점수 >=30이면 type="플래티넘",ratio = 0.07 / 점수 >=20이면 type="골드",ratio=0.05||`두 개의 명령문을 실행시 사용 X`
||type = "플래티넘"
||ratio = 0.07
||} `else if`(score >=20){
||type = "골드"
||ratio = 0.05
||}
|subset|df_1 <- `subset`(iris,Species `==` "setosa")|
|인덱스|df_2 <- iris`[`iris$Species `==` "setosa" `,]`
|filter|df_3 `%>% filter`(iris$Species `==` "setosa")
---
### `반복문`
|함수|코드|예시|결과|의미|
|---|---|---|---|---|
|for|for (반복 변수 in 반복 범위) {|for (i in 1:10){|1 2 3 4 5 6 7 8 9 10|i를 1~10까지 10번 반복
||반복할 명령문(들)|print(i)
||}|}

---
### **`데이터 합치기`**
#### - **`paste 함수`**
|코드|paste|결과|해석|비고|
|---|---|---|---|---|
|str5 <-c("Hello!", "World", "is", "good!")|
||`paste`( str5, `sep =` ",")|"Hello!Worldisgood!"|`sep()` :  문자열을 이어붙일 때 사용하는 구분자를 지정
||`paste`( str5, `collapse =` ",")|"Hello!,World,is,good!"|`collapse()`: 결과를 하나의 문자열로 결합할 때 사용|`paste()는 여러 개의 문자열이나 숫자값을 결합하여 하나의 문자열로 만드는 기능을 한다`
|a <- 1:12
|b <- "월"
||c <- `paste`(a,b,sep='')
||"1월"  "2월"  "3월"  "4월"  "5월"  "6월"  "7월"  "8월"  "9월"  "10월" "11월" "12월" |벡터 a에 있는 값을 차례로 가져와 b와 연결후 새로운 벡터에 저장|
|score.1 <- 68; score.2 <- 95; score.3 <- 83; score.4 <- 76; score.5 <- 90; score.6 <- 80; score.7 <- 85; score.8 <- 91; score.9 <- 82; score.10 <- 70
|total <- c(68,95,83,76,90,80,85,91,82,70)
|num1 <- c(1:10)
|s1 <- "score."|
||item1 <- `paste`(s1,num1,sep="");item1|
|names(total) <- item1;total|| score.1(68)  score.2(95)  score.3(83)  score.4(76)  score.5(90)  score.6(80)  score.7(85)  score.8(91)score.9(82) score.10(70)|값 추가하기
---
#### - **`stack 함수`**
|함수|코드|의미|
|---|---|---|
|stack()|comb <- `stack`(list(fresh = freshmen, soph = sophomores, jrs = juniors))|집단을 합치기|
---
### **`파생 변수 생성 함수`**
|함수|코드|의미|
|---|---|---|
|mutate|exam_tot <-
||exam %>%
||mutate(total =  math + english + science, mean = (math + english + science)/3)|mutate를 사용해서 total이라는 파생 변수를 생성|
|summarise|summarise(`mean1 = mean(score),median1 = median(score)`)|mean과 median과 같은 `내장 함수를 사용하여 파생 변수와 요약본을 생성`|