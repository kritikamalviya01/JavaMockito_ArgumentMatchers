Mocking Lists in Java using Mockito


Mockito is a popular mocking framework in Java that allows you to create mock objects for testing. 
Mocking allows you to create objects with predefined behavior, which can be useful for isolating and testing specific parts of your code. 
Mocking lists is a common scenario in unit testing, as lists are often used to store and manipulate data.

Mocking List Size

One of the most common ways to mock a list is to mock its size. This can be done using the `when()` method of Mockito. For example:

java:
List list = mock(List.class);
Mockito.when(list.size()).thenReturn(10);
assertEquals(10, list.size());


In this example, we're creating a mock list called `list`. We then use the `when()` method to specify that when the `size()` method is called on this list,
it should return the value `10`. We then call the `size()` method on the list and assert that the result is `10`.

Mocking List Get

We can also mock the behavior of the `get()` method of a list. For example:


List<String> list = mock(List.class);
Mockito.when(list.get(0)).thenReturn("Kritika");
assertEquals("Kritika", list.get(0));
assertNull(list.get(1));


In this example, we're creating a mock list of strings called `list`. We then use the `when()` method to specify that when the `get()` method is called on this 
list with the argument `0`, it should return the value `"Kritika"`. We then call the `get()` method on the list with the argument `0` and assert that the result
is `"Kritika"`. We also call the `get()` method on the list with the argument `1` and assert that the result is `null`, since we haven't specified any behavior
for this case.

Argument Matchers

Mockito provides a number of argument matchers that can be used to match arguments passed to mocked methods.
This can be useful when you want to specify more complex matching criteria. For example, you can use the `anyInt()` matcher to match any integer value:


List<String> list = mock(List.class);
when(list.get(anyInt())).thenReturn("Kritika");
assertEquals("Kritika", list.get(0));
assertEquals("Kritika", list.get(1));


In this example, we're using the `anyInt()` matcher to specify that the `get()` method should return `"Kritika"` for any integer value passed as an argument.

Argument Matchers with Exceptions

You can also use argument matchers to specify that a mocked method should throw an exception. For example:

java
List<String> list = mock(List.class);
when(list.get(anyInt())).thenThrow(new RuntimeException("Error"));
list.get(0);


In this example, we're using the `anyInt()` matcher to specify that the `get()` method should throw a `RuntimeException` with the message
`"Error"` for any integer value passed as an argument. We then call the `get()` method on the list, which will cause the test to fail with a `RuntimeException`.



Mocking lists in Java using Mockito is a powerful technique that can be used to isolate and test specific parts of your code. By using mock lists,
you can control the behavior of the list and ensure that your tests are not affected by external factors.
