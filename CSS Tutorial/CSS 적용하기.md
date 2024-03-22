# CSS Tutorial

> HTML이 콘텐츠의 구조와 의미를 정의하는 반면 CSS는 스타일과 레이아웃을 지정합니다.  
> https://developer.mozilla.org/ko/docs/Learn/CSS

css는 속성과 값으로 이루어져있다

```css
/* 속성: 값 */
height: 1000px;
```

## CSS 적용하기

1. style 속성 사용하기
2. style 태그 사용하기
3. css 선택자
4. css 파일 만들기

## style 속성 사용하기

### 태그에 style 속성을 추가

```html
<h1 style="color: red">빨간색</h1>
```

예시코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS style 속성 사용하기</title>
  </head>
  <body>
    <h1 style="color: red">빨간색</h1>
    <h1 style="color: orange">주황색</h1>
    <h1 style="color: yellow">노란색</h1>
    <h1 style="color: green">초록색</h1>
    <h1 style="color: blue">파란색</h1>
    <h1 style="color: navy">남색</h1>
    <h1 style="color: purple">보라색</h1>
  </body>
</html>
```

여러 스타일 추가

> 여러 스타일을 추가할때는 세미콜론(;)으로 구분

```html
<h1 style="color: red; background-color:black;">빨간색</h1>
```

## style 태그 사용하기

> style 속성은 스타일이 많아지면 코드가 지저분해진다!

```html
<!-- 너무 길어.. -->
<h1
  style="color: red;background-color: aliceblue;border-width: 2px;border-radius: 2rem;margin: 10rem;padding: 10rem;"
>
  빨간색
</h1>
```

### style 태그를 사용해보자

```html
<style>
  h1 {
    color: red;
    background-color: aliceblue;
  }
</style>
```

예시 코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS style 태그 사용하기</title>
    <style>
      h1 {
        color: red;
        background-color: aliceblue;
      }
    </style>
  </head>
  <body>
    <h1>빨간색</h1>
  </body>
</html>
```

## CSS 선택자

CSS 선택자란?

> CSS 속성 값을 적용할 HTML을 선택하는 규칙

CSS 선택자를 이용해서 한번에 여러개 요소(태그)에 스타일을 적용해보자

### 1. 태그 선택자

- 태그이름을 이용해 선택

```css
태그이름 {
  color: red;
}
```

예시 코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS 스타일 태그 사용하기</title>
    <style>
      h1 {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>빨간색</h1>
    <h1>빨간색</h1>
    <h1>빨간색</h1>
    <h1>빨간색</h1>
  </body>
</html>
```

### 2. 클래스 선택자

- 클래스이름을 이용해 선택

태그에 class 속성 추가

```html
<div class="red-letters">빨간색</div>
<div class="red-letters">빨간색</div>
```

class 속성은 언제 사용할까?

- 여러 태그를 묶어서 스타일이나 인터랙션을 추가할 때 (같은 class 속성이 여러개 있을 수 있다)

클래스 선택자

- "."을 클래스 이름 앞에 붙임

```
.클래스이름{
  color: red;
}
```

예시 코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS 스타일 태그 사용하기</title>
    <style>
      .red-letters {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1 class="red-letters">빨간색</h1>
    <h1 class="red-letters">빨간색</h1>
    <h1>검은색</h1>
    <h1>검은색</h1>
  </body>
</html>
```

### 3. 아이디 선택자

- 아이디를 이용하여 선택

태그에 id 속성 추가

```html
<h1 id="blue-letters">파란색</h1>
```

id 속성은 언제 사용할까?

- 하나의 요소에 스타일이나 인터랙션을 추가할 때 (id는 겹칠 수 없다)

아이디 선택자

- "#"을 아이디 앞에 붙임
- 아이디 선택자가 클래스 선택자보다 우선시됨

```css
#아이디 {
  color: red;
}
```

예시 코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS 스타일 태그 사용하기</title>
    <style>
      .red-letters {
        color: red;
      }
      #blue-letters {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1 id="blue-letters" class="red-letters">파란색</h1>
    <h1 class="red-letters">빨간색</h1>
    <h1>검은색</h1>
    <h1>검은색</h1>
  </body>
</html>
```

css 선택자 예시코드

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>CSS 스타일 태그 사용하기</title>
    <style>
      div {
        background-color: lawngreen;
      }

      .box {
        color: red;
      }

      #main-box {
        color: blue;
      }
    </style>
  </head>
  <body>
    <div id="main-box" class="box">박스1</div>
    <div class="box">박스2</div>
    <div class="box">박스3</div>
    <div>박스 아님</div>
  </body>
</html>
```
