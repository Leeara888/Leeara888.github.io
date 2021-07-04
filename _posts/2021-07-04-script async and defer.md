**1.스크립트를 헤드에 포함한다면?**

````html
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자바스크립트 1일차</title>
    <script src="main.js"></script>
</head>
````

html 다운중 스크립트를 보게 된다면 실행을 멈추고 자바스크립트를 다운받는다.

-> 스크립트 파일이 크거나 인터넷이 느리면 많은시간이 소요된다.





**2.스크립트를 바디끝에 넣는다면?**

```html	
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자바스크립트 1일차</title>
    
</head>
<body>
    <div></div>
    <script src="main.js"></script>
</body>
</html>
```

페이지가 준비가 완료가 된 후 스크립트가 실행됨

-> html은 빠르게 볼 수있으나 자바스크립트가 많이 들어간 프로그램(동적인 웹사이트)이 로드 될때까지

기다려야한다.



**head + async**	

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자바스크립트 1일차</title>
    <script async src="main.js"></script>
    
</head>
<body>
    <div></div>
</body>
</html>
```

`async `  는  `**boolean**` 속성값이라 선언 하는것 만으로 true 값으로 설정된다.

`body` 태그 끝에 있는것 보다는  병렬로 다운을 받아 시간이 빠를 수는 있지만

 -> `html` 을 다운받기 전에 `javascript` 가 먼저 실행이 완료되 

`javascript` 가 필요로 하는 `html`이  로드가 안될 수 있어 위험하다.

 -> `javascript` 가 실행이 되기위해서 멈출수있어  다운이 느려질 수 있다.



**head + defer **

````html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>자바스크립트 1일차</title>
    <script defer src="main.js"></script>
    
</head>
<body>
    <div></div>
</body>
</html>
````

`html` 이 다운로드 되는동안 `javascript` 를 다운 받아 놓고 

페이지를 보여준 후 `javascript`를 실행한다.

**현재 까지는 가장 효율이 좋다**



**use strict**

````javascript
console.log('hello world!');

a = 6;
````

`use strict`를 선언하지 않고 작업하게 된다면 

선언 되지 않은 변수값을 할당하면 브라우저에서는 문제가 없지만



```javascript
'use strict';
console.log('hello world!');

a = 6;
```



`use strict`를 선언하고 작업하면 

브라우저에서 할당되자 않은 변수값이라고 오류가 생긴다.
