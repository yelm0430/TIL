# form
- form은 형식을 나타내는 코드

```python
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
   
</head>
<body>
    <h1>Form</h1>
    # method ="get" => 여기 있는 입력 데이터는 남들이 봐도 상관없다
    # method = "post" => 여기 있는 입력 데이터는 보이면 안된다

    <form action="URL" method="POST">
        <div>
            <label for="username">username</label>
            <input type="text"id="username"required autofocus>
        </div>
        # 이때,<label for="username">과 id="username"이 같아야 한다. id의 username에 기반하여 lable을 하겠다는 의미
        # required : 무조건 작성 해야한다
        # autofocus : 처음에 해당 label에 커서가 위치한다

        <div>
            <label for="password">password</label>
            <input type="password" id="password">
        </div>
        # 이때,<label for="password"> 와 id="password"이 같아야 한다 


        <div>
            <label for="my-email">email</label>
            <input type="email" id ="my-email" placeholder="email은 @를 포함합니다">
        </div>
        # 이때, <label for="my-email">과id ="my-email"이 같아야 한다
        # placeholder : 해당 label에 기본으로 작성되는 문장이 위치한다. 단, 해당 form의 결과에 영향 X
                      # ex ) email : 'email은 @를 포함합니다' 기본적으로 위치
```
## form의 type
|type|의미|사용법|
|---|---|---|
|number|숫자|`<input type="number" id ="age" value ="20">`|
|checkbox|체크박스|`<input type="checkbox" value ="apple"> 사과`|
|radio|선택|`<input type="radio" name ="gender" value ="F"> 여자`|
|submit|제출|`<input type="submit" value ="얍!">`|
|color|색상|



        <div>
            <label for="age">age</label>
            <input type="number" id ="age" value ="20">
        </div>

        <div>
            <input type="checkbox" value ="apple"> 사과
            <input type="checkbox" value ="banana"> 바나나
            <input type="checkbox" value ="strawberry"> 딸기
        </div>

        <div>
            <input type="submit" value ="얍!">
        </div>

        <div>
            <input type="radio" name ="gender" value ="F"> 여자
            <input type="radio" name ="gender" value ="M"> 남자
            <input type="radio" name ="gender" value ="N"> 둘다 아님

        </div>

    </form>

    <div>
        <input type="color">
        <input type="email">
        <input type="number">
        <input type="radio">
        <input type="checkbox">
        <textarea name="" id="" cols="30" rows="10"></textarea>


    </div>

    <hr>

    <form action=""></form>
</body>
    
</html>
```