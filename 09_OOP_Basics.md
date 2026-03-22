# အခန်း (၉) - OOP အခြေခံ (Class, Object, Constructor, Encapsulation, Package)

---

## ဒေအခန်းပြီးကေ ဇာသိရဖို့လဲ?

- Class နန့် Object ကွာခြားချက်ကို နားလည်လာဖို့
- Constructor ကိုသုံးပြီးကေ object initialize လုပ်နိုင်လာဖို့
- Encapsulation (`private` + getter/setter) ကို အသုံးချနိုင်လာဖို့
- `package` နန့် `import` ကို beginner level မှာ မှန်ကန်စွာ သုံးနိုင်လာဖို့
- OOP mindset ကို beginner အဆင့်မှာ မှတ်သားနိုင်လာဖို့

---

## OOP Concepts (overview)

Java OOP ဧ အခြေခံ concepts ၄ ခု:
- Encapsulation
- Inheritance
- Polymorphism
- Abstraction

ဒေအခန်းမှာ first step အနီနန့် Class/Object/Constructor/Encapsulation ကို ဦးစားပီးပါဖို့။

---

## Class ဆိုစွာ ဇာလဲ?

Class = blueprint/template
Object = blueprint အထဲကနီ ဖန်တီးထားရေ real instance

```java
class Student {
    String name;
    int age;

    void introduce() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}
```

---

## Object ဖန်တီးနည်း

```java
public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();
        s1.name = "Aung Aung";
        s1.age = 20;
        s1.introduce();

        Student s2 = new Student();
        s2.name = "Su Su";
        s2.age = 19;
        s2.introduce();
    }
}
```

---

## Constructor

Constructor က object ဖန်တီးရေအချိန်မှာ auto-run ဖြစ်ပါရေ။

Rule:
- Name = class name
- Return type မရီးရပါ

```java
class Student {
    String name;
    int age;
    double gpa;

    Student(String name, int age, double gpa) {
        this.name = name;
        this.age = age;
        this.gpa = gpa;
    }

    void showInfo() {
        System.out.println(name + " | " + age + " | " + gpa);
    }
}
```

```java
Student s = new Student("Mg Mg", 21, 3.9);
s.showInfo();
```

---

## `this` Keyword

Parameter name နန့် field name တူနီရေခါ `this.fieldName` လိုသုံးပါ။

```java
class Car {
    String brand;

    Car(String brand) {
        this.brand = brand;
    }
}
```

---

## Encapsulation

Data ကို directly expose မလုပ်ဘဲ methods မှတဆင့် access/control လုပ်စွာကို encapsulation လို့ခေါ်ပါရေ။

```java
class BankAccount {
    private String owner;
    private double balance;

    BankAccount(String owner, double initialBalance) {
        this.owner = owner;
        this.balance = initialBalance;
    }

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0) {
            balance += amount;
        }
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance) {
            balance -= amount;
        }
    }
}
```

---

## Package နန့် Import (Beginner Must-Know)

`package` ဆိုစွာ class တိကို folder/group ခွဲစည်းဖို့ နည်းလမ်းဖြစ်ပါရေ။
Project ကြီးလားလာခါ package မခွဲထားကေ class တိရှုပ်ထွေးလားတတ်ပါရေ။

### Example folder structure

```text
src/
  com/course/model/Student.java
  com/course/app/Main.java
```

`Student.java`

```java
package com.course.model;

public class Student {
    public String name;

    public Student(String name) {
        this.name = name;
    }
}
```

`Main.java`

```java
package com.course.app;

import com.course.model.Student;

public class Main {
    public static void main(String[] args) {
        Student s = new Student("Aung Aung");
        System.out.println(s.name);
    }
}
```

### Terminal နန့် compile/run

```bash
javac -d out src/com/course/model/Student.java src/com/course/app/Main.java
java -cp out com.course.app.Main
```

---

## Access Modifier Quick View

| Modifier | Same Class | Same Package | Subclass | Other Package |
| :--- | :---: | :---: | :---: | :---: |
| `private` | Yes | No | No | No |
| *(default)* | Yes | Yes | No | No |
| `protected` | Yes | Yes | Yes | No |
| `public` | Yes | Yes | Yes | Yes |

**မှတ်ရန်:** access control ကို package နန့်တွဲပြီး စဉ်းစားရပါရေ။

---

## Class vs Object Summary

| Class | Object |
| :--- | :--- |
| Blueprint | Real instance |
| Structure define လုပ်ရေ | Memory ယူပြီး data ကိုင်ရေ |
| `class Car {}` | `Car c1 = new Car();` |

---

## အဖြစ်များရေ အမှားတိ

```java
Student s;
// s.introduce(); // compile error: local variable not initialized

Student s2 = null;
// s2.introduce(); // NullPointerException

Student(String name) {
    name = name;      // wrong
    this.name = name; // correct
}

package com.app;
import java.util.Scanner;
package com.model; // Error: package statement တစ်ဖိုင်မှာ တစ်ကြိမ်ရာ
```

---

## အခန်းချုပ်

- Class/Object concept က OOP entry point ဖြစ်တေ
- Constructor နန့် object initialization ကို safe ပုံစံနန့်လုပ်နိုင်ရေ
- Encapsulation သုံးကေ data integrity ကောင်းလာရေ
- Package/Import သုံးကေ project structure ပိုစနစ်တကျဖြစ်လာရေ

---

## လေ့ကျင့်ခန်းတိ

1. `Rectangle` class မှာ `width`, `height` fields ထည့်ပြီးကေ `area()` method ရီးပါ
2. `Person` class မှာ `private name`, `private age` နန့် getter/setter ရီးပါ
3. `Car` class ကို constructor နန့် object ၃ ခု တည်ဆောက်ပါ
4. `BankAccount` class မှာ deposit/withdraw validation ထည့်ပါ
5. `com.school.model` နန့် `com.school.app` package ၂ ခုခွဲပြီး class ၂ ခုကို `import` နန့်ဆက်သွယ်ပါ
