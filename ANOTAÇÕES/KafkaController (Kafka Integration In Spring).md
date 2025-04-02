
```java
@RestController
public class KafkaController {

    @Autowired
    private MessageProducer messageProducer;

    @PostMapping("/send")
    public String sendMessage(@RequestParam("message") String message) {
        messageProducer.sendMessage("lasteste", message);
        return "Message sent: " + message;
    }
}
```