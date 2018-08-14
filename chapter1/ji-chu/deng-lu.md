```
protected void configure(HttpSecurity http) throws Exception {
    http.authorizeRequests()  //通过authorizeRequests方法来开始请求权限配置
    .anyRequest()  //拦截所有http请求
    .authenticated() //权限验证，用户登录后可以访问
    .and() //返回一个securityBuilder对象
    .formLogin() 
    .and()
    .httpBasic();
}
```



