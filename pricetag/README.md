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







