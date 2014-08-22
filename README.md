Tacones
=======

Tacones is a Java Library to add some OWL properties characteristics to Java language.

A simple example:

```java
public class Person {

    @Property(name = "hasPet")
    private Pet pet;

    @SymmetricProperty
    private Person friend;

}

public class Pet {

    @InverseOf(property = "hasPet")
    private Person owner;
}

```

With this annotations we have some advantages like OWL does with inferences:

```java
Person a = new Person("Andres");
Person b = new Person("Pilar");
a.setFriend(b);

assertEquals(a,b.getFriend());

Pet pet = new Pet("Tomcat");
a.setPet(pet);

assertEquals(a,pet.getOwner());

```

