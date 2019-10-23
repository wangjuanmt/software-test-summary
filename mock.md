# Mock platform for Java

## Mockito
官网：https://site.mockito.org/

git: https://github.com/mockito/mockito

文档：https://static.javadoc.io/org.mockito/mockito-core/3.1.0/org/mockito/Mockito.html

````java
import static org.mockito.Mockito.*;

// mock creation
List mockedList = mock(List.class);

// using mock object - it does not throw any "unexpected interaction" exception 
mockedList.add("one");
mockedList.clear();

// selective, explicit, highly readable verification 验证
verify(mockedList).add("one");
verify(mockedList).clear();
````

打桩：
````java
// you can mock concrete classes, not only interfaces
LinkedList mockedList = mock(LinkedList.class);

// stubbing appears before the actual execution
when(mockedList.get(0)).thenReturn("first");

// the following prints "first"
System.out.println(mockedList.get(0));

// the following prints "null" because get(999) was not stubbed
System.out.println(mockedList.get(999));
````

## JMockit
官网：http://jmockit.github.io/index.html

````
class ExampleTest {
   @Tested ServiceAbc tested;
   @Injectable DependencyXyz mockXyz;

   @Test
   void doOperationAbc(@Mocked AnotherDependency anyInstance) {
      new Expectations() {{
         anyInstance.doSomething(anyString); result = 123;
         AnotherDependency.someStaticMethod(); result = new IOException();
      }};

      tested.doOperationAbc("some data");

      new Verifications() {{ mockXyz.complexOperation(true, anyInt, null); times = 1; }};
   }
}
````

## References
https://stackoverflow.com/questions/22697/whats-the-best-mock-framework-for-java

https://www.vogella.com/tutorials/Mockito/article.html

https://dzone.com/articles/the-concept-mocking

