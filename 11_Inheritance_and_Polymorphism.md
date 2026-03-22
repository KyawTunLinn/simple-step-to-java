# အခန်း (၁၁) - Inheritance နန့် Polymorphism

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- `extends` နန့် parent/child relationship တည်ဆောက်နိုင်လာဖို့
- Method overriding ကို မှန်ကန်စွာ သုံးနိုင်လာဖို့
- Polymorphism နန့် flexible code design ကို နားလည်လာဖို့
- `super` keyword ကို သင့်တော်ရေ နီရာမှာ အသုံးချနိုင်လာဖို့

---

## Inheritance ဆိုစွာ ဇာလဲ?

Inheritance ဆိုစွာ class တခုက အခြား class တခုဧ properties/methods ကို အမွီယူ (reuse) လုပ်စွာဖြစ်ပါရေ။

- Parent class (Super class)
- Child class (Sub class)

```java
class Animal {
    void eat() {
        System.out.println("Animal can eat");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}
```

```java
Dog d = new Dog();
d.eat();  // from parent
d.bark(); // child own method
```

---

## ၁) `super` keyword

Parent class constructor (သို့) method ကို ခေါ်ဖို့ `super` ကိုသုံးပါ။

```java
class Person {
    String name;

    Person(String name) {
        this.name = name;
    }
}

class Student extends Person {
    int rollNo;

    Student(String name, int rollNo) {
        super(name);
        this.rollNo = rollNo;
    }
}
```

---

## ၂) Method Overriding

Child class က parent method ကို logic အသစ်နန့် ပြန်သတ်မှတ် (override) လုပ်လို့ရရေ။

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Meow");
    }
}
```

`@Override` annotation သုံးထားကေ method signature မှားယွင်းမှုကို compile time မှာမြင်ရလွယ်ပါရေ။

---

## ၃) Polymorphism (Parent reference, Child object)

```java
class Animal {
    void sound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Woof");
    }
}

class Bird extends Animal {
    @Override
    void sound() {
        System.out.println("Tweet");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Bird();

        a1.sound(); // Woof
        a2.sound(); // Tweet
    }
}
```

**Idea:** code ရေးရာမှာ parent type (`Animal`) ကိုသုံးထားကေ future classes တိုးလာလေ maintain လုပ်ရလွယ်လာပါရေ။

---

## Overloading vs Overriding

| Feature | Overloading | Overriding |
| :--- | :--- | :--- |
| နီရာ | Same class | Parent + Child |
| Method name | Same | Same |
| Parameters | Different | Same |
| Runtime behavior | Compile-time binding | Runtime polymorphism |

---

## အဖြစ်များရေ အမှားတိ

```java
class A {
    void run(int x) {}
}

class B extends A {
    @Override
    void run() {} // Error: signature မတူ
}
```

```java
class Parent {
    private void show() {}
}

class Child extends Parent {
    // private method ကို override လုပ်လို့မရ
}
```

```java
Animal a = new Animal();
Dog d = (Dog) a; // Runtime: ClassCastException
```

---

## အခန်းချုပ်

- Inheritance နန့် code reuse လုပ်နိုင်ရေ
- Overriding + Polymorphism နန့် flexible architecture ဖန်တီးနိုင်ရေ
- `super` နန့် parent constructor/method ကို safe ပုံစံနန့်ခေါ်နိုင်ရေ

---

## လေ့ကျင့်ခန်းတိ

1. `Vehicle` parent class နန့် `Car`, `Bike` child class တည်ဆောက်ပြီး `start()` ကို override လုပ်ပါ
2. `Employee` parent နန့် `Developer`, `Accountant` child class ရီးပြီး `calculateSalary()` ကို polymorphism နန့် run ပါ
3. Constructor inheritance နန့် `super(...)` သုံးထားရေ example တခု ရီးပါ
4. Overloading နန့် overriding ကို နှိုင်းယှဉ်ပြရေ code ၂ ခုစီ ရီးပါ
