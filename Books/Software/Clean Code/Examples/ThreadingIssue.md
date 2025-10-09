threading can be an issue.

even if the code is as simple as that:

ClassWithThreadingProblemTest.java 
```java
import org.junit.jupiter.api.Test;  
  
import static org.junit.jupiter.api.Assertions.fail;  
  
public class ClassWithThreadingProblemTest{  
    @Test  
    public void twoThreadsShouldFailEventually() throws Exception{  
        final ClassWithThreadingProblem classWithThreadingProblem = new ClassWithThreadingProblem();  
        Runnable runnable = new Runnable(){  
            public void run(){  
                classWithThreadingProblem.takeNextId();  
            }  
  
        };  
        for(int i=0; i<80000; i++){  
            int startingId = classWithThreadingProblem.nextId;  
            int expectedResult = 2 + startingId;  
            Thread t1 = new Thread(runnable);  
            Thread t2 = new Thread(runnable);  
            t1.start();  
            t2.start();  
            t1.join();  
            t2.join();  
            int endingId = classWithThreadingProblem.nextId;  
            if (endingId != expectedResult)  
                return;  
        }  
        fail("Should have exposed a threading issue but it did not");  
    }  
}
```

ClassWithThreadingProblem.java
```java
public class ClassWithThreadingProblem {  
    int nextId;  
    public int takeNextId(){  
        return nextId++;  
    }  
}
```

Running this once, you cant be sure about whats the output, but if you run this 10 times you can be sure it will not output the same result each time.

this is a not an [[Atomic instruction]], thats the issue;