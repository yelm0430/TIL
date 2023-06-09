# markdown 기초

## 제목 설정

|코드|설명|
|---|---|
|#|문서에서 가장 큰 제목|
|##|문서에서 2번째 큰 제목|
|###|문서에서 3번째 큰 제목|
|####|문서에서 4번째 큰 제목|
|#####|문서에서 5번째 큰 제목|
|######|문서에서 6번째 큰 제목|
---
## 리스트
### 순서가 있는 리스트(ordered list)
1. 8시 기상
    - 유산균 먹기
        - 공복에 하루 1알
    - 양배추즙 먹기
    - 양치하기
    - 옷갈아입기

2. 9시 수업듣기
    - 아이패드 세팅하기
        - 줌 입장
    - 노트북 세팅하기


---
## 내용

|코드|설명|
|---|---|
|**A**|두껍게|
|*A*|기울기|
|`code`|코드작성|
|~~A~~|취소선|

---
## 링크
|코드|설명|
|---|---|
|`[]`|표시하고 싶은 부분|
|`()`|소괄호|

ex) 만약 네이버 링크를 만들고 싶다면?

[네이버](https://naver.com/)

---
## 이미지
### 작성 순서 : ! => [] => ()

ex) ![dog](https://vitapet.com/media/sz1czkya/benefits-of-getting-a-puppy-900x600.jpg)

---
## 표 작성
|이름|사는곳|관심|
|---|---|---|
|장예림|시흥|커피|
|홍*길*동|서울|`여행`|

---
## 인용문
> 아직 피어있지 않았어도 때론 비에 젖어있어도 예쁘네.
우리는 아마 그럴걸

> 자세히 보아야 예쁘다
---
## 코드 블럭
```python
import zhimport webbrowser

webbrowser.open('naver.com')
```
---
## 수식 블럭
$$
\begin{aligned}
E[(X-m_X)(Y-m_Y)]&=E[XY-m_XY-m_YX+m_Xm_Y]\
&=E[XY]-m_XE[Y]-m_YE[X]+m_Xm_Y\
&=m_Xm_Y-m_Xm_Y-m_Ym_X+m_Xm_Y=0\
\therefore\rho=0
