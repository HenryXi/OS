# Linux curl command examples
`curl` is a good tool to help you make a request. Before introducing how to use it we need to start a server which receives
the requests. I use `Spring Boot` as a simple server. The code is like following.

```java
@Controller
@EnableAutoConfiguration
public class CurlExampleController {
    @RequestMapping(value = "/hello", method = RequestMethod.GET)
    @ResponseBody
    public String hello(@RequestParam(value = "name") String name) {
        return "Hello " + name + "\n";
    }

    @RequestMapping(path = "/post-json", method = RequestMethod.POST)
    @ResponseBody
    public String postXml(@RequestBody User user) throws IOException {
        return user.toString();
    }

    public static void main(String[] args) {
        SpringApplication.run(CurlExampleController.class, args);
    }
}
```

Use `curl` to make `Get` request and post json to server.

```bash
[root@virtual tmp]# curl 192.168.56.1:8080/hello?name=henry
Hello henry
[root@virtual tmp]# curl --header "Content-Type: application/json" --request POST --data '{"name":"henry","age":29}' 192.168.56.1:8080/post-json
User{name='henry', age='29'}
```

EOF