# project1-2024
2024-2학기 캡스톤프로젝트 수업  

![js](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=JavaScript&logoColor=white)
![js](https://img.shields.io/badge/CSS-239120?&style=for-the-badge&logo=css3&logoColor=white)
![js](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![js](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)
![js](https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white)

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

![스크린샷 2024-10-29 130129](https://github.com/user-attachments/assets/476555a3-579c-40e0-9f9b-d6fcb16a3c9a)

# openAI
chatGPT API키 활용하여 질의응답
[실습해보기1](https://api.openai.com/v1/chat/completions),
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

![스크린샷 2024-10-23 235045](https://github.com/user-attachments/assets/284e5699-2080-4e0b-be29-cd8d8a58ec7c)

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

# 캡스톤 프로젝트 중간 과제
2024-10-23

# GOOGLE API를 이용한 이미지 분석
이 프로젝트는 사용자가 업로드한 이미지를 GOOGLE  VISION API 키를 통해 이미지 확인 후 감정을 분석해 주는 코드.

# 기능
- 이미지 업로드
- 이미지 분석
- 얼굴 감지
- 감정 분석

# 사용방법 
1. 이미지 업로드
2. 이미지 분석 버튼 클릭
3. 분석한 감정을 %단위로 출력
