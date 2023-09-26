# Calling a Void Method

In the last section we discussed how to create an object using constructors, and now that we have objects, we want to be able to use them to perform actions. The behavior of an object, or the actions it can perform, are called **methods**.

In this section we won't be making our own methods for objects, but rather will be understanding how to use ones that are already written. The concept of **procedural abstraction** refers to the idea that we can understand how to use a method and what it accomplishes without knowing how it was written, or in general how it functions in the background.

---

## Method Signatures

Just like constructors, methods have unique **signatures**, made up of their names and parameter lists. In this section, we focus on methods that have empty parameter lists, so the differentiators for signatures will just be the method names. Here is an example `Person` class with a couple of methods from `Person.java`

```java
public class Person {
    private int age;
    private boolean isStudent;

    public Person(int a, boolean s){
        age = a;
        isStudent = s;
    }

    public void sayAge(){
        System.out.println(age);
    }

    public void sayIsStudent(){
        System.out.println(isStudent);
    }
}
```

We can see here that there are two methods, called `sayAge` and `sayIsStudent`, which just function as simple print statements. The keyword **`void`** is important here, as it lets us know that the method does not **return** information to wherever it was called to, and instead just performs it's action.

---

## Calling Methods

It is important to understand what happens to a program when a method is called upon. We saw above the impementation of the `Person` class, which describes the `sayAge` and `sayIsStudent` method for us to use. Here is a sample from `NotesMethodCall1.java` which creates an object and calls both methods:

```java
Person person1 = new Person(25, false);
person1.sayAge();
person1.sayIsStudent();
```

Normally in a program, we think of it as running through line-by-line and performing whatever the code states. Things like object methods break this sequential program flow and sends the program over to the class that the method is from to execute it there, before coming back to where the method was called and continuing. So here, the first line sends it over to `Person.java` to create a `Person`, comes back to save the reference to a variable, then is sent off again to `sayAge`, comes back, and is sent off one more time to `sayIsStudent`.

Just like with `System.out.println`, we use the dot operator `.` with an object to call its methods, and have to use parentheses after the method name to indicate that we are not sending any parameters.

This sample will print the following:

```
25
false
```

---

## `null` Keyword Update

Since we can have a way to intialize variables as `null` when we don't have an object for them yet, it is important to consider what would happen if we accidentally try to call a method with a `null` reference, which we can see happen in the `NotesNull1.java` file:

```java
Person person1 = null;
person1.sayAge();
```

We can see something is going to go wrong as Visual Studio Code points this out as a warning, but doesn't stop us from running it. Here is what happens if we try to run this:

```
Exception in thread "main" java.lang.NullPointerException: Cannot invoke "Person.sayAge()" because "person1" is null
        at NotesNull1.main(NotesNull1.java:4)
```

This is known as a **`NullPointerException`**, and will prevent the rest of our code from being run.

---

## Assignment

Now that you have gone through the notes for this section, you can check out the `Try.md` and `Try.java` files to try a short assignment using this material.
