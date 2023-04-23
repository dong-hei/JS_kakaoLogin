(자바스크립트)카카오 로그인 API 적용하기

Kakao Developers 사이트 접속 >
1. 내 애플리케이션 > 애플리케이션 추가하기 > 앱 추가하면 앱키가 등록된다.
2. 내 애플리케이션 > 앱 설정 > 플랫폼 > 사이트 도메인 등록
3. 내 애플리케이션 > 제품 설정 > 카카오 로그인 > 활성화 상태 ON , Redirect URI 등록
4. 내 애플리케이션 > 제품 설정 > 카카오 로그인 > 동의항목 > 개인정보 동의항목 설정

<바디부>
<script src="https:/developers.kakao.com/sdk/js/kakao.js"></script>
5. JavaScript SDK 파일을 웹 페이지에 포함시킨다.

<a href="javascript:kakaoLogin();"><img src="https://developers.kakao.com/tool/resource/static/img/button/login/full/ko/kakao_login_medium_narrow.png"></a>
6. 카카오 로그인 버튼

window.Kakao.init("부여 받은 js 키를 입력!");
7. 카카오 부여받은 JS키 입력

function kakaoLogin(){}
8. 콜백 함수

function kakaoLogin(){함수 안의 내용}
scope:'profile_nickname, account_email, gender',
9. 동의항목에 체크한 내용들 scope

success: function(authObj){
window.Kakao.API.request({
url:'/v2/user/me',
success: res =>{const kakao_account = res.kakao_account;}
10. 인증 성공했을때 콜백함수 (카카오 Docs에 있는 내용과 같다.)

            
            
