# springboot-security-oauth

1.访问localhost:8081/oauth/authorize?client_id=client&response_type=code&redirect_uri=http://www.baidu.com
访问时Spring让你登陆,输入用户名admin密码123456即可。 注意, 如果每次登陆时输入的用户名不一样,那么Spring Security会认为是不同的用户,因此访问/token/authorize会再次显示授权页面。如果用户名一致, 则只需要授权一次

2.拿到code再使用postman请求
curl -X POST -H "Content-Type: application/x-www-form-urlencoded" -d 'grant_type=authorization_code&code=Li4NZo&redirect_uri=http://www.baidu.com' "http://client:secret@localhost:8081/oauth/token"
