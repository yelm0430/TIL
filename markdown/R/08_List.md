# 리스트
### 리스트 : 데이터 프레임과 달리 길이(항목의 개수)가 달라도 사용 가능
#### `리스트 작성`
|코드|결과|설명|
|---|---|---|
|cafe <- list(espresso=c(4,5,3,6,5,4,7)`,` americano=c(63,68,64,68,72,89,94)`,`latte=c(61,70,59,71,71,92,88)`,`price=c(2.0,2.5,3.0)`,`menu=c("espresso","americano","latte"))|$espresso
||[1] 4 5 3 6 5 4 7
||$americano
||[1] 63 68 64 68 72 89 94
||$latte
||[1] 61 70 59 71 71 92 88
||$price
||[1] 2.0 2.5 3.0
||$menu
||[1] "espresso"  "americano" "latte" 
|cafe$menu <- factor(cafe$menu)
|names(cafe$price) <- cafe$menu
|sale.espresso <- cafe$price["espresso"]*cafe$espresso
|sale.americano <- cafe$price["americano"]*cafe$americano
|sale.latte <- cafe$price["latte"]*cafe$latte
|sale.espresso|8 10  6 12 10  8 14
|sale.americano|157.5 170.0 160.0 170.0 180.0 222.5 235.0
|sale.latte|183 210 177 213 213 276 264
|sale.day <- sale.espresso + sale.americano + sale.latte
|names(sale.day) <- c("Mon","Tue","Wed","Thu","Fri","Sat","Sun")|  Mon   Tue   Wed   Thu   Fri   Sat   Sun |요일별 매출액
||348.5 390.0 343.0 395.0 403.0 506.5 513.0 
|sum(sale.day)|2899|총매출액
|sale.mean <- mean(sale.day)|414.1429|평균 매출액
|names(sale.day[sale.day>=sale.mean])|"Sat" "Sun"|평균 매출액 이상인 요일 추출
