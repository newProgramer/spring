# 创建一个简单的security

### 1. 引入依赖

```
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-security</artifactId>
</dependency>
```

### 2. 继承WebSecurityConfigurerAdapter

```
public class SecurityConfiguration extends WebSecurityConfigurerAdapter {

    @Override
    protected void configure(AuthenticationManagerBuilder auth) throws Exception {
        super.configure(auth);
    }

    @Override
    public void configure(WebSecurity web) throws Exception {
        super.configure(web);
    }

    @Override
    protected void configure(HttpSecurity http) throws Exception {
        super.configure(http);
    }
}
```

> 查看protected void configure\(HttpSecurity http\) throws Exception的源码
>
> ```
> protected void configure(HttpSecurity http) throws Exception {
>     http.authorizeRequests()  //通过authorizeRequests方法来开始请求权限配置
> 	.anyRequest()  //拦截所有http请求
> 	.authenticated() //权限验证，用户登录后可以访问
> 	.and() //返回一个securityBuilder对象
> 	.formLogin() 
> 	.and()
> 	.httpBasic();
> }
> ```



