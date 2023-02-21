# 0220 웹해킹_
## f12 버튼으로 개발자 도구 열기
### devtool_sources 문제
- 개발자 도구를 열어 ctrl+shift+f 를 통해 전체 검색을 하여 flag를 찾았다
- 문제 형식이 정해져 있어서 쉬운 문제였음

![image](https://user-images.githubusercontent.com/48954288/220221255-1a38cec1-9f60-4487-84f9-8f3321bc1d33.png)

## session과 cookie
- 세션을 사용하여 타 계정의 권한 취득
- 쿠키는 클라이언트가 임의로 조작 가능 (ex)세션 id를 바꾸는 것
### session_basic 문제
- 먼저 py파일이 있어 열어봄 --> flask 파일

![image](https://user-images.githubusercontent.com/48954288/220221746-562eee2c-2a67-45f2-859e-012b0c299c98.png)
- user 정보가 있어 로그인해 보았지만 admin이 아니면 할 수 있는게 없었음

![image](https://user-images.githubusercontent.com/48954288/220221780-d7c5469c-6425-489a-b48b-4fb1f5324e89.png)
- flask파일을 아래로 내리던 중 app.route를 찾음
- session_storage를 반환 --> 루트를 타고 들어가면 session id 값을 받을 수 있겠다

![image](https://user-images.githubusercontent.com/48954288/220222050-e613ef88-1403-4eaf-b453-b418bf89a290.png)

- 먼저 로그인 창에 들어간 뒤 /login --> /admin --> 유저 별 세션id를 확인할 수 있었다

![image](https://user-images.githubusercontent.com/48954288/220222559-6e33169c-95b9-4966-892b-da16691f49ce.png)
- guest, guest로 로그인 한뒤, 개발자 도구를 열어 Application에서 session id 를 admin의 session id로 변경
- flag값 도출

![image](https://user-images.githubusercontent.com/48954288/220222792-6b6b1a07-788c-4bcb-a744-e279fcb8d891.png)

### cookies 문제
- 위 문제와 같이 flask 파일에 user 정보

![image](https://user-images.githubusercontent.com/48954288/220223591-a7fd7536-d9ef-42c4-ba82-764eab9cb39f.png)

- username이 쿠키로 저장되고, username에 대해 페이지에서 return 하는 값이 달라짐

![image](https://user-images.githubusercontent.com/48954288/220223935-db3db087-a78c-47df-a96a-498434a966ad.png)

- guest로 로그인해서 username을 admin으로 수정
- flag값 도출

![image](https://user-images.githubusercontent.com/48954288/220224021-6a9dc26c-bad4-46c8-bfc2-d5796199bf38.png)


