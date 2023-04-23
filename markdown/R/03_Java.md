# R과 JAVA연동
### `경로 설정`
|설명|코드|예시|`주의사항`|
|---|---|---|---|
|directory 확인|getwd()|setwd("`/`Users`/`jang-yelim`/`R_TEMP`/`yelim`/`")|한 번만 `/` 사용|
|directory 변경|setwd("**현재 directory**")|setwd("`\\`Users`\\`jang-yelim`\\`R_TEMP`\\`yelim`\\`")| 두 번 사용시 `\\` 사용
|경로 설정|Sys.setenv(JAVA_HOME="자바 경로명")|Sys.setenv(JAVA_HOME="/Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home")
|경로 확인|Sys.getenv("JAVA_HOME")|Sys.getenv("JAVA_HOME")