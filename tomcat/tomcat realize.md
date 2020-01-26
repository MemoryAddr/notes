# Tomcat Realize

## 技术使用

- 服务端暴露端口：socket网络编程
- 给每个请求分配线程：BIO线程模型
- 解析HTTP协议的请求，根据解析到的uri调用不同的servlet：http协议
  - http请求体（/r/n）
  - http响应体
- 加载和接信息项目中的servlet：servlet规范

## 核心

服务端ServerSoket，获取客户端Soket，然后获取Soket的InpustStream和OutputStream，将其包装为Request和Response对象，再结合Servlet.service()方法实现对web访问操作，让开发者更加专注于业务。

