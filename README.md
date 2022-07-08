# 카카오 API 사용해보기

목록

- [카카오지도](#카카오지도)
- []()

## #카카오지도

#### 1.카카오 개발자 가입 (개발자 등록 및 앱 생성)<br>

[https://apis.map.kakao.com/](https://apis.map.kakao.com/)

<br>

#### 2.애플리케이션 추가하고, 웹 플랫폼에 주소 입력하기 (사이트 도메인 등록)

<br>

#### 3.지도 가져오는 cdn 추가

\_실행 코드보다 먼저 선언되어야 함

```html
<script
  type="text/javascript"
  src="//dapi.kakao.com/v2/maps/sdk.js?appkey=발급받은 APP KEY를 넣으시면 됩니다."
></script>
```

<Br>

#### 4.지도를 담을 영역 만들기<br>

```html
<div id="map" style="width:500px;height:400px;"></div>
```

<br>

#### 5.지도를 띄우는 코드 작성 (실행코드)

```js
//지도를 담을 영역의 DOM 레퍼런스
var container = document.getElementById("map");

//지도를 생성할 때 필요한 기본 옵션
var options = {
  //지도의 중심좌표.
  center: new kakao.maps.LatLng(33.450701, 126.570667),

  //지도의 레벨(확대, 축소 정도)
  level: 3,
};

//지도 생성
var map = new kakao.maps.Map(container, options);
```

<br>

#### 6.현재 위치를 기준으로 지도 가져오기

```js
// 현재 위치 정보 가져오기
navigator.geolocation.getCurrentPosition((pos) => {
  // 위도, 경도
  const x = pos.coords.latitude;
  const y = pos.coords.longitude;

  var options = {
    center: new kakao.maps.LatLng(x, y),
    level: 3,
  };

  var map = new kakao.maps.Map(container, options);
});
```

<br>

> 참고 <br> > [참고사이트\_현재 위치 정보 가져오기](https://inpa.tistory.com/entry/JS-%F0%9F%93%9A-Geolocation-API%EB%A1%9C-%F0%9F%97%BA%EF%B8%8F-%EC%9C%84%EB%8F%84-%EA%B2%BD%EB%8F%84-%EC%96%BB%EA%B3%A0-%E2%9B%85-%EB%82%A0%EC%94%A8-%EC%98%A8%EB%8F%84-%EC%A0%95%EB%B3%B4%EB%A5%BC-%EC%96%BB%EC%96%B4%EC%98%A4%EA%B8%B0)
