## 가격표 만들기

이 **코딩**의 핵심은 

1. 미디어쿼리를 적용해서 화면 크기에따라서 display가 바뀌어 보이게 만드는 것
2. flexbox를 이용해서 가격표의 정렬을 바꾸는 것

일단 완성을 보여주자면

![](https://velog.velcdn.com/images/whkfk12/post/2815b898-28d4-415a-8f85-abd868db2756/image.gif)

보시다시피 화면이 줄어들면 세로로 정렬하게 만들었고,
화면의 너비가 늘어나면 가로로 배열되게 만들었다.

이 부분의 미디어 쿼리를 어떻게 줬냐면
``` Html

@media (min-width: 900px){
    .panel {
    flex-direction: row;
    }
    .pricing-plan {
    border-bottom: none;
    border-right: 1px solid #e1f1ff;
    padding: 25px 50px;
    }
    .pricing-plan:last-child {
    border-right: none;
    }
}
```
이렇게 적용 시켜주면 `panel`부분의 정렬 방식이 900px를 넘어가면 가로로 정렬이 된다. 

그리고 이걸 코딩하면서 제일 헷갈렸던 부분은
```Html
.pricing-features-item {
    font-weight: 600;
    letter-spacing: 1px;
    font-size: 12px;
    line-height: 1.5;
    padding: 15px 0;
    border-top: 1px solid #e1f1ff;
}

.pricing-features-item:last-child{
    border-bottom: 1px solid #e1f1ff;
}
```
이 부분이었는데 이상하게 `border-bottom` 부분과 `border-top`의 선이 안나타나 .panel부분도 확인했다. 갑자기 선이 생기긴했는데 내가 정확하게 어떻게 해결한건지가 어려웠다_(ㅠㅠ)_

그리고 버튼의 디자인을 가운데만 다르게 적용하는것도 애를 좀 먹긴했는데 클래스 선택자를 만들어서 그 부분만 새롭게 적용하니까
계단식 적용이라 밑에 적은 선택자가 적용되어서 , 가운데만 버튼이 다르게 뜰 수 있었다 !

```HTML
.pricing-button.is-featured {
    background-color: #48aaff;
    color: white;
}

.pricing-button.is-featured:hover, .pricing-button.is-featured:focus{
    background-color: #269aff;
    color: white;
```

일단 미디어 쿼리를 이욧해서 가로 세로 정렬과 
CSS를 마치긴 했는데 한번 더 복습이 필요 할 것 같다

vw와 vh도 여기에서 사용된다는걸 어제 공부한 부분을 다시 복습한 코딩이 되었고 ! 내가 미디어쿼리에대해서 헷갈리거나 그러면 다시 돌아와서 연습 할 수 있는 코드가 될  같다.

이건 전체 완성샷 !

![](https://velog.velcdn.com/images/whkfk12/post/c19d4521-eab5-4e49-adc2-c94498b6809d/image.png)


## 사탕 박물관 프로젝트

이건 **부트스트랩**을 이용해서 **반응형 웹 페이지**를 만드는 과제! 앞에서 그동안 배운 특성을 부트스트랩을 이용해서 간단하게 위치를 지정하고 상대적으로 창의 크기가 줄어들고 넓어질때마다 배열이 달라지게 만드는게 목표였다.


> navigation

일단 navigition 부분을 만들려고 부트스트랩을 이용해서 마크업 했다.

![](https://velog.velcdn.com/images/whkfk12/post/706953ff-2297-4bf8-8b8b-058e3954afeb/image.png)

여기서 중요했던건 `data-target`을 목록과 잘 이어주는 부분이었다.
CSS로는 전체 배경화면을 깔아주고, navbar의 가장 큰 로고가 될 부분과 다른 부분의 차이를 두는 것과 마우스를 호버 했을때 색이 변하는 효과를 줬다. 그리고 `py-0`으로 y축 패딩을 0으로 주었다.
그리고 화면이 작아질수록 메뉴가 바짝 붙는걸 대신해서 toggler로 담기게 만들어줬다. 

![](https://velog.velcdn.com/images/whkfk12/post/dc45c572-a002-46b3-9f04-9a371f614b80/image.png)

만든 모습은 이렇게 볼 수 있다. 저 햄버거 모양 선 세개를 누르면 내가 만들어놓았던 메뉴들을 누를 수 있다. 그리고 아무리 스크롤을 해도 navbar가 상단에 뜨도록 `fixerbar-top`을 적용 시켜주었다. _하지만 여기에서 저렇게 적용해두니 내용들과 메뉴가 겹쳐서 내려가는 현상이 발생했다(ㅠㅠ)_ 

> Section

+ heading section

일단 다음 밑에 내용 section부분은 **그리드**를 이용했고, 이미지는 **fluid**를 적어줘서 유동적으로 크기가 늘어나고 줄어들 수 있게 적용시켰다.

![](https://velog.velcdn.com/images/whkfk12/post/5b898037-5a97-40cc-9d60-268bfa517d19/image.png)


`class="row"`로 줘서 나열시키고 `col-6`으로 주어서 이렇게 텍스트를 화면의 절반만 차지하도록 했다. 색상은 하얀색 중앙 정렬 `d-none`으로 창이 작아지면 텍스트가 보이지 않도록 만들었고, 커진 경우에만 보이게 해줬다. 여기에서 아까 네비게이션 부분과 내용이 겹치는게 해결이 되었다. 그리고 / 슬래쉬 부분만 빨간 색을 주고 싶어서 `<span>`으로 묶어주고 id선택자로 헤딩 그룹을 주었다. 그렇게 7개로 복사해서 콘텐츠를 만들어 주었다. 그랬더니 위가 답답하게 붙어서 `mt-5`로 위에 여백을 주었다.

그러고 나서 미디어쿼리를 이용해서 창이 줄어들대마다 어떻게 반응할지 CSS에 적어주었다.

```html
@media (max-width: 1200px) {
    #headingGroup h1 {
        font-weight: 100;
        font-size: 3rem;
    }
```

+ 하단 section

위쪽과 똑같이 가로로 배치하고 옆쪽에 여백을 만들지 않았다. 이것도 `px-0`으로 주면 간단하고. 이미지와 텍스트 부분이 5 : 5로 나뉘기 때문에 `col-6`으로 나누어주었다. 여기도 당연히 이미지에 fluid를 적용 시켜주었다.

![](https://velog.velcdn.com/images/whkfk12/post/0d6236d4-82b7-4f26-89a6-9b303eb5f47d/image.png)

가운데 정렬를위해 행에 수직정렬을 넣어주고 flexbox를 이용해서 `lign-items`를 이용해 중앙에 모았다. 창이 줄어들었을때 텍스트 부분을 완전히 가운데로 정렬해주기위해서 이미지를 제외한 부분에서 문자가 들어가는 부분을 col-10으로 주었고 나머지 여백이 1씩, 그러고 나서 justify-content로 다시 수직정렬하니까 좀 좁아 보여서 8로 수정해주었다.

![](https://velog.velcdn.com/images/whkfk12/post/bc3dfcbe-3872-49a6-926e-390aa256a782/image.png)

그렇게하면 위의 사진처럼 텍스트가 창이 작아져도 딱 중앙에 알맞게 정렬되는 걸 볼 수 있다.
그리고 아이콘은 창이 커지면 보이고 작아지면 보이지 않도록 display를 설정해주었다.사진부분과 텍스트 부분을 위치 나열을 위해 `order-1`과 `order-2`를 주었고 중간을 넘으면 첫번째가 이미지 창이 작아지면 글씨가 오도록 정해주었다.

![](https://velog.velcdn.com/images/whkfk12/post/b111815c-005b-407d-87e0-9350e88fd164/image.gif)

창이 클 때는 이미지가 먼저 오지만 작아지면 글이 먼저 오도록 한 것 !
h2에 blurb를 주어서 단락마다 css를 적용 시킬 수 있도록 했고, 모든 폰트 사이즈는  rem을 적용 시켜주었다. 단락의 간격도 line-height를 주어 보기 좋게 해주었다. 

```html
.content {
    margin-top: 100px;
    margin-bottom: 100px;
}
```

마지막으로는 단락 사이의 여백을 넓혀주려고 했는데 CSS에서 섹션과 섹션 사이를 넓혔다. 그 부분을 content로 클래스 선택자를 주고 margin으로 여백을 주었다. 
_다른 단락은 복붙해서 붙여주고 이미지를 바꿔주었다._

근데 하단 여백을 다 주고 나니까 너무 어정쩡해져서 여백을 없애는 것도 입력해주었다

> navigation scroll

CSS에서 스크롤을 정해주고 배경색을 주고, 자바스크립트 파일을 따로 만들지 않고 아래에 코드를 쳤다. 

![](https://velog.velcdn.com/images/whkfk12/post/65b292f0-0d13-478a-849d-4050170fe51c/image.png)

스크롤 동작이 발생하면 네비게이션을 확인하라는 코드를 넣고,  변수이름 $nav 입력하고
토글 클래스에 스크롤을 넣고 ` $(this).scrollTop() > $nav.height()` 를 입력해주었다. 
페이지가 스크롤 될때마다 nav보다 위에있는지를 확인하라는거다.

사실 이부분은 자바스크립트와 제이쿼리가 섞여서 나는 잘 이해하지 못하지만,
나중에 다시 돌아보면 알 것 같다.

#### 완성 된 전체 모습

![부트스트랩 반응형](https://github.com/user-attachments/assets/0ac7ad1a-98ea-422c-9ad6-e1d68274e144)





