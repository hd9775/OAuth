# OAuth

### application.properties
```
#jpa
spring.jpa.hibernate.ddl-auto=create
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true
spring.jpa.defer-datasource-initialization=true

#include
spring.profiles.include=oauth, datasource

#jwt
oauth.jwt.secret=//secretKey
oauth.authorizedRedirectUri=http://localhost:8080/user/oauth/token
```

### application-datasource.properties
```
spring.datasource.username=//id
spring.datasource.password=//pwd
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
spring.datasource.url=//url
```

### application-oauth.properties
```
#Kakao
spring.security.oauth2.client.registration.kakao.client-id=//api key
spring.security.oauth2.client.registration.kakao.redirect-uri=http://localhost:8080/oauth2/callback/kakao
spring.security.oauth2.client.registration.kakao.authorization-grant-type=authorization_code
spring.security.oauth2.client.registration.kakao.scope=account_email,profile_nickname
spring.security.oauth2.client.registration.kakao.client-name=Kakao
spring.security.oauth2.client.registration.kakao.client-authentication-method=POST

#Kakao Provider
spring.security.oauth2.client.provider.kakao.authorization-uri= https://kauth.kakao.com/oauth/authorize
spring.security.oauth2.client.provider.kakao.token-uri=https://kauth.kakao.com/oauth/token
spring.security.oauth2.client.provider.kakao.user-info-uri=https://kapi.kakao.com/v2/user/me
spring.security.oauth2.client.provider.kakao.user-name-attribute=id
```
