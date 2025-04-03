
```java
@Component
public class MessageConsumer {
   @KafkaListener(topics = "lasteste", groupId = "1")
   public void ouvir(String mensagem) {
       System.out.println("Mensagem recebida: " + mensagem);
   }
}
```