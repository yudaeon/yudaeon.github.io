# 어노테이션

## 주요 어노테이션

### **`@Component`**

개발자가 직접 작성한 Class를 Bean으로 등록하기 위한 어노테이션이다.

```bash
@Component
public class Student {
    public Student() {
        System.out.println("hi");
    }
}
```

### **`@Bean`**

개발자가 직접 제어가 불가능한 외부 라이브러리 등을 Bean으로 만드려할때 사용하는 어노테이션이다.

```bash
@Configuration
public class ApplicationConfig {
    @Bean
    public ArrayList<String> array(){
        return new ArrayList<String>();
    }
}
```

### **`@Controller`**

스프링의 컨트롤러를 의미한다.

### **`@Service`**

서비스 클래스에서 쓰인다. 비즈니스 로직을 수행하는 Class라는 것을 나타내는 용도이다.

### **`@SpringBootApplication`**

@Configuration, @EnableAutoConfiguration, @ComponentScan 3가지를 하나의 애노테이션으로 합친 것이다.

### **`@Configuration`**

@Configuration 클래스에 적용하고 @Bean을 해당 Class의 method에 적용하면 @@Autowired로 Bean을 부를 수 있다.

### `@RequestMapping`

: 특정 URL로부터 요청을 받으면 어떤 Controller에서 처리할 지 알아야 한다.

이 때, 특정 url을 요청을 수행할 Controller와 매핑하여 지정하는 어노테이션이다. 

### `@RequestParam`

Controller 메소드의 파라미터와 웹요청 파라미터와 매핑하기 위한 어노테이션

### `@ModelAttribute`

Controller 메소드의 파라미터나 리턴값을 Model 객체와 바인딩하기 위한 어노테이션

### `@SessionAttributes`

Model 객체를 세션에 저장하고 사용하기 위한 어노테이션

### `@RequestPart`

Multipart 요청의 경우, 웹요청 파라미터와 맵핑가능한 어노테이션(egov 3.0, Spring 3.1.x부터 추가)

### `@CommandMap`

Controller메소드의 파라미터를 Map형태로 받을 때 웹요청 파라미터와 맵핑하기 위한 어노테이션(egov 3.0부터 추가)

### `@ControllerAdvice`

Controller를 보조하는 어노테이션으로 Controller에서 쓰이는 공통기능들을 모듈화하여 전역으로 쓰기 위한 어노테이션(egov 3.0, Spring 3.2.X부터 추가)

---

## 요청방식

### `@GetMapping`

💡 **GET 방식 : 어떠한 정보를 가져와서 조회하기 위해 사용되는 방식**

- Get방식은 url에 아이디, 비밀번호, 이름 등이 노출된다. 이것에 대한 해결방안으로 Post방법을 사용하면 된다.

▪ URL에 변수를 포함시켜 요청한다.

▪ 데이터를 header를 포함하여 전송한다.

▪ URL에 데이터가 노출되어 보안에 취약하다.

▪ 캐싱이 가능하다. (캐싱: 한번 접근후, 똑같은 요청을 할 시 빠르게 접근하기 위해 레지스터에 데이터를 저장시키는것)

### `@PostMapping`

💡 **POST 방식: 데이터를 서버로 제출하여 추가 또는 수정하기 위해서 데이터를 전송하는 방식**

▪ URL에 변수에 변수를 노출하지 않고 요청을 한다.

▪ 데이터를 Body에 포함시킨다.

▪ U**RL에 데이터가 노출되지 않아서 기본 보안이 설정되어 있다.**

▪ 전송하는데 길이 제한이 없고 캐싱이 불가능하다.