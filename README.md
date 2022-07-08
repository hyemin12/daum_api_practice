# 카카오 API 사용해보기

목록

- [카카오지도](#카카오지도)
- []()

## #카카오 지도

1. 카카오 개발자 가입 (개발자 등록 및 앱 생성)<br>
   [https://apis.map.kakao.com/](https://apis.map.kakao.com/)

2. 애플리케이션 추가하고, 웹 플랫폼에 주소 입력하기 (사이트 도메인 등록)

3. 지도 가져오는 cdn 추가

<span style="color:red">실행 코드보다 먼저 선언되어야 함</span>

```html
<script
  type="text/javascript"
  src="//dapi.kakao.com/v2/maps/sdk.js?appkey=발급받은 APP KEY를 넣으시면 됩니다."
></script>
```

4. 지도를 담을 영역 만들기<br>

```html
<div id="map" style="width:500px;height:400px;"></div>
```

5. 지도를 띄우는 코드 작성 (실행코드)

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

6. 현재 위치를 기준으로 지도 가져오기

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
