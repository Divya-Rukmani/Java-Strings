# More about Java Strings

Are you wondering what am I going to pen down about the Java Strings? Most of you would probably come across these string execution, but I bet many of you don’t. This article is to the people of the second category. I will explain you from the scratch for the betterment.

## Getting Started

String is a sequence of characters. In other words, Java String is basically an array of characters.
Strings are introduced in JDK 1.0. Java strings are immutable. What in the world is immutable mean? Let me put it in simpler words. Java Strings are immutable which means the object values cannot be changed after they are created.


## Ways to Create a String in Java:

There are two ways to create a string in Java:

Using String literals
1.By using new keyword.
2.Using String Literal:

Trust me, before writing this article, I actually believed that this is the only way to create a string in Java.

```
String str1="Hello World";
```
And, you can create a string by using new Keyword too.

```
String str2= new String("Hello world");
```

So what makes the difference in both. I will explain you better considering different scenarios:

## Scenario 1:

```
String str1="Hello world";
String str2="Hello world";
System.out.println(str1 == str2); /// true
System.out.println(str1.equals(str2)); // true
```

In this case, str1 is saved in string constant pool. When str2 is created, it will check "Hello world" literal is already available in StringPool or not. Now "Hello world" already exists so str2 will refer to the same literal and no new objects are created.

![1_rbydcnso02yozxktm69niq](https://user-images.githubusercontent.com/30400247/43757343-242983d8-9a36-11e8-89d0-1196a2db5e70.png)

## Scenario 2:

```
String str1=new String("Hello world");
String str2=new String("Hello world");
System.out.println(str1 == str2);// false
System.out.println(str1.equals(str2));//true
```

In this case str1 and str2 objects are saved in different heap because we use new Keyword. So str1==str2 tends to be false since it is object comparison and str1.equals(st2) returns true because the contents of both objects are the same.

![1_dozlgmv8v8qiiws882frzq](https://user-images.githubusercontent.com/30400247/43757430-621d4206-9a36-11e8-95cd-deee0cf06122.png)


## Scenario 3:

```
String str1="Hello world";
String str2=new String("Hello world");
System.out.println(str1 == str2);// false
System.out.println(str1.equals(str2));//true
```

![1_eltcw28ytngyctzt7oylvg](https://user-images.githubusercontent.com/30400247/43757555-bec581da-9a36-11e8-8ad0-ca68330b74d8.png)

As I said before, str1 is created in constant pool since it is string literal and str2 object is created in heap because of new keyword. So the comparison str1==str2 returns false because objects referred by both variables are different. And str1.equals(str2) returns true since the contents of the objects are same.

### Benefits of String Immutability:

* It is thread safe.
* It is secured because the object values can’t be changed once created.





 

