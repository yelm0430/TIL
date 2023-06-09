# R 기초 정리
### `경로 설정`
|설명|코드|예시|`주의사항`|
|---|---|---|---|
|directory 확인|getwd()|setwd("`/`Users`/`jang-yelim`/`R_TEMP`/`yelim`/`")|한 번만 `/` 사용|
|directory 변경|setwd("**현재 directory**")|setwd("`\\`Users`\\`jang-yelim`\\`R_TEMP`\\`yelim`\\`")| 두 번 사용시 `\\` 사용
|경로 설정|Sys.setenv(JAVA_HOME="자바 경로명")|Sys.setenv(JAVA_HOME="/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home")
|경로 확인|Sys.getenv("JAVA_HOME")|Sys.getenv("JAVA_HOME")
---
### `데이터 분석 정리 단축키`
|코드|의미|설정|예시
|---|---|---|---|
|`fontfamily="AppleGothic")|맥에서 한글꺠짐`|
|read.csv("경로",`fileEncoding = "euc-kr"`)|`파일 불러올시 오류발생시`|
|ctrl + enter|실행
|ctrl + shift + c|선택한 부분 주석처리
|ctrl + 2|console 창으로 이동
|ctrl + 1|스크립트 창으로 이동
|ctrl + l|콘솔 모두 클리어
|option + (-)|<- 생성
|ctrl + shift + n |새 스크립트 열기
|ctrl + O | 파일 열기
|(ctrl + shift + m)|파이프라인
|getwd()|현재 작업이 실행되고 directory 확인|
----

### `에러 발생 시`
- 콘솔 창에 +가 나올시 esc로 탈출해서 `>` 가 나와야 함
----

### `변수 삭제`
|코드|의미|
|---|---|
|rm ( list=ls() )|변수 전체 삭제 
|rm (변수명)|특정 변수 삭제
----
### `변수 확인`
|코드|의미|
|---|---|
|ls()|현재 활성화 되어있는 변수 목록 확인 
|ls (변수명)|특정 데이터셋의 변수 확인
----

### `변수 삽입`
|코드|결과|
|---|---|
|num <- ( 2,5 )|에러
|num <- `c`( 2,5 )|2,5
---
### `그래프 그리는 시각화 패키지`
|코드|의미|주의할점|
|---|---|---|
|install.packages("ggplot2")|시각화 패키지 설치|단 한 컴퓨터에 한번만 설치|
|library(ggplot2)|시각화 패키지 실행|컴퓨터 실행시 매일 설치|
----
### `패키지 관련 코드`
|코드|의미|
|---|---|
|search()|현재 실행 중인 패키지 확인|
|remove.packages("패키지명")|패키지 삭제|
----

### `변수명 작명 규칙`
- 첫 글자는 영문자나 마침표로 시작
- 첫 글자에 숫자 사용 X
- 변수명에 대소문자를 구분
- 변수명 중간에 빈 칸 사용 X
----
## `변수에 저장 될 수 있는 값의 종류`
|변수형|코드|결과|`주의할점`
|---|---|---|---|
|논리형|2 < 7|True|
||True + True|1|
|결측값|NA|NA|`"na"안됌`
---
### `행과 열  바꾸기`
|코드|의미|비고|
|---|---|---|
|matrix <- c((1,2,3,4,5,6,7,8),nrow=2, `byrow=True`)|맨 처음 데이터 구조를 설정 시 사용|
|변수 <- `t`(변수명)|행과 열 바꾸기|대각선을 기준으로 값을 바꿔줌|
---
#### - **`변수명 변경 및 추가`**
- `변수명 변경`

|코드|관련 코드|예시|의미|
|---|---|---|---|
|library(tidyverse)사용
||`rename(data,신변수명 = 구변수명)`|mpg_new <- rename(mpg_new,city=cty,highway=hwy)|mpg_new에서 cty는 (city)로, hwy는 (highway)로 변수명을 수정하세요.
|tolower|names(iris_lower) <- tolower(names(iris))||항목이름 소문자 변경


- `새로운 변수 추가(파생변수)`

|코드|의미|
|---|---|
|df_new`$(새로운 변수명)` <- df_new$v1 + df_new$v2|v1과 v2 더하는 add 변수 추가
