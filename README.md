# project1-2024
2024-2학기 캡스톤프로젝트 수업  
openAPI를 사용한 인공지능 시스템 실습

# openweathermap

지정된 장소의 현재 날씨를 표시
[실습해보기](https://api.openweathermap.org/data/2.5/weather?q=london&units=metric&appid=7d96bc5108f52b80e2d9075a369b9f35)

```javascript
$.ajax({
         type: "GET",
         url: 'https://api.openweathermap.org/data/2.5/weather?q=london&units=metric&appid=7d96bc5108f52b80e2d9075a369b9f35',
      }).done(function(response) {

            console.log(response)
            }).fail(function(error) {
         alert("!/js/user.js에서 에러발생: " + error.statusText);
      });


```
# openAI
chatGPT API키 활용하여 질의응답
[실습해보기1](https://api.openai.com/v1/chat/completions)
[실습해보기2](https://api.openai.com/v1/images/generations)
        

```javascript
  $.ajax({
        type:"POST",
        url: "https://api.openai.com/v1/chat/completions",
        headers:{
            "Authorization": "Bearer " + OPENAPI_KEY
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){
        console.log(response)
        alert(response.choices[0].messge.content)
    }).fail(function(error){
        console.log(error)
        errormsg = error.status + " : " + error.responseJSON.error.code + " - " + error.responseJSON.error.code.messages
        alert(errormsg)
    }) 
```

```javascript
$.ajax({
        type:"POST",
        url: "https://api.openai.com/v1/images/generations",
        headers:{
            "Authorization": "Bearer " + OPENAPI_KEY
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){
        console.log(response)
        // alert(response.choices[0].message.content)
        gimage.src = response.data[0].url
        gimage2.src = response.data[1].url
    }).fail(function(error){
        console.log(error)
        errormsg = error.status + " : " + error.responseJSON.error.code + " - " + error.responseJSON.error.message
        txtOut.value = errormsg
    })
```

# google cloud vision
구글 api키를 이용하기
[실습해보기](https://vision.googleapis.com/v1/images:annotate?key=)

```javascript
 $.ajax({
        type:"POST",
        url:'https://vision.googleapis.com/v1/images:annotate?key=' + GOOGLE_API_KEY,
        headers:{
            "Accept": "application/json",
            "Content-Type": "application/json"
        },
        data: JSON.stringify(data),
        contentType: "application/json; charset=utf-8"
    }).done( function(response){    
        console.log(response)

    }).fail(function(error){
        console.log(error)

    })
```
1. 소스 수정
2. 소스 저장
3. 스테이지
4. 커밋에 푸쉬
5. 커밋메시지

git 설정
git config--global user.name "soek345"
git config--global user.email "tkddbstjrdbs123@g.shingu.ac.kr"
git confi--list

두번째 수정


2024-9-19 깃허브연동실습
2024-10-18 google vision api 키를 사용해 얼굴인식후  (웃음,슬픔,화남,놀람)표정 감지

로컬에서 편집함

개발순서
1. 소스 수정
2. 소스 저장
3. 스테이지
4. 커밋&푸시
5. 커밋메시지

깃 설정

git config --global user.name "name"
git config --global user.email "email@naver.com"

2024-09-19 깃허브 연동수업
로컬에서 편집함
