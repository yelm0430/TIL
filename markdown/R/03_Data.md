# Data
### **`- 데이터구조`**
|데이터구조|차원|형태|특징|
|---|---|---|---|
|벡터(vector)|1차원|단일형|한 가지 변수 타입으로 구성
|팩터(factor)|1차원||범주형 자료일때 사용
|리스트(List)|1차원|다중형|서로 다른 데이터 구조 포함
||||`변수의 길이가 동일하지 않아도 된다`
|데이터 프레임(Dataframe)|2차원|다중형|다양한 변수 타입으로 구성
||||`변수의 길이가 동일해야 한다`
|매트릭스(Matrix)|2차원||한가지 변수 타입으로 구성
|어레이(Array)|다차원|단일형|2차원 이상의 매트릭스

---
### **`- 데이터 정제 `**
|의미|코드|예시|의미|비고|
|---|---|---|---|---|
|**결측치 확인**|
||is.na()|table(is.na(df$score))|점수 na의 유무 확인
|**결측치 제거**|
||filter()|filter(!is.na(score)) & !is.na(sex)|na를 제외한 score과 sex값 추출
||na.rm()|sum(df$score,na.rm = T)|score에서 na값을 제외한 합계|`na값을 가진 변수를 제외한 나머지` 값 추출
|||||`데이터에는 존재하나 통계분석시에만 사용된다`|
||na.omit()|||모든 변수에서 `na값이 존재하는 행 삭제`

---
### **`- 데이터의 입출력 `**
|코드|의미|주의사항|예시|결과|
|---|---|---|---|---|
|cat()|여러 개의 값을 연결해서 출력할 때|`"n\"`을 사용하여 수동으로 줄 바꿈 해야함|
|||벡터는 출력가능하나 2차원 자료구조는 출력 X|cat("제 이름은 ",name,"입니다.",sep="")|제 이름은 장예림입니다.
|print()|하나의 값을 출력할 때|출력 후 자동 줄 바꿈
|||2차원 자료구조 출력시 사용
---
### **`- 파일불러오기 및 저장 `**
|코드|의미|주의사항|
|---|---|---|
|`m_csv <- read.csv("../data/month_50.csv.")`|csv 파일 불러오기|
|`write.csv(month_50, "../data/month_50.csv.", row.names = FALSE)`|csv 파일로 저장하기|`row.names = FALSE`로 저장시 첫번째 열 삭제|
---
#### - **`데이터 시각화 하기`**
|종류|함수|특징|예시|해석|사용 가능 인자|
|---|---|---|---|---|---|
|다양한 시각화|qplot|전처리 단계 데이터 확인용|||
||ggplot|최종 보고용(색, 크기, 폰트 등 세부조작 가능)| ggplot(data = mpg, aes(x=displ, y = hwy)||
||||ggplot(data = mpg, aes(x=displ, y = hwy)) + geom_point() + xlim(3,7) + ylim(10,30)|
||||ggplot(data=df_mpg, aes(x = reorder(drv,`-`mean_hwy), y = mean_hwy)) + geom_col()|`mean을 기준으로 내림차순 정렬한 순서대로 그래프 보여주기`
|막대그래프|geom_col|`평균 막대 그래프` : 데이터를 요약한 평균표를 만든 후 그 결과를 기반으로 그래프 생성
||geom_bar|`빈도 막대 그래프` : 별도의 표를 만들지 않고 원자료를 이용해 그래프 생성|ggplot(data = df, aes(x = reorder(manufacturer,-mean_cty), y = mean_cty)) + `geom_bar(stat = "identity")`||mapping : aes() 함수를 통해 정의된 미지정한 매핑과 함께 사용
||||||stat : 통계적 계산 방법을 지정합니다. identity로 지정하면 입력 데이터를 사용하여 막대 생성 
||||||position : 막대를 어떻게 위치시킬지를 지정합니다. dodge로 지정하면, 막대를 분리하여 나란히 그리며 stack으로 지정하면, 막대를 겹쳐서 그립니다.
||||||fill : 막대의 색상을 지정합니다.
||box plot|1) 집단 간 분포 차이를 표현|||
|||2) 평균보다 데이터의 특성을 이해할수 있음|
|산점도|xyplot|데이터를 x축과 y축을 기준으로 산점도로 표현|xyplot(ozone ~ wind : month, data = aq_melt, layout = c(5,1))||
|선그래프|geom_line()|경제 지표가 시간에 따라 어떻게 변하는지 표현할 때 활용|ggplot(data = economics, aes(x = date , y = unemploy)) + geom_line()|