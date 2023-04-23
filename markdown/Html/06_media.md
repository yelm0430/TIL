# HTML_Media

### image
- Image Tag : 속성이 Inline으로 문장 중간에 삽입이 가능하다.
- if ) 이미지를 삽입하고 싶다면?
```python
    - <p>
       1)
        <img src="./red_panda_wink.jpg" alt="래서판다" width="600px">
        # src뒤에는 `./` 작성후 가져올 사진의 이름 작성
        # 만약, 사용할 이미지가 다른 파일에 있다면 `../`을 작성 후 사진 이름 작성
        # alt의 의미는 오류 발생시 사진 대신에 보여줄 글자
    <br>
    
        2)
        <img src="https://i.pinimg.com/736x/25/c8/ed/25c8ed6febb9769ff5d232518c457bea.jpg" alt="래서판다" width="600px">  
    </p>
```

### iframe
- 퍼오고 싶은 영상의 주소를 가지고 오기
```python
<h2>Iframe
        <iframe
            width="650"
            height="315"
            src="https://www.youtube.com/embed/qAg6fTVu8gI" 
            title="YouTube video player" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
            allowfullscreen
        >
        </iframe>
```