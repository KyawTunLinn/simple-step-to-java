# အခန်း (၇) - Methods (Functions)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Code ကို methods ခွဲရီးပြီးကေ clean design ရနိုင်လာဖို့
- Parameters, return values ကို မှန်ကန်စွာ သုံးနိုင်လာဖို့
- Method overloading နန့် scope ကို နားလည်လာဖို့
- Reusable logic တည်ဆောက်နိုင်လာဖို့

---

## Method ဆိုစွာ ဇာလဲ?

Method ဆိုစွာ အလုပ်တခုကို သီးသန့်လုပ်ပီးရေ code block ဖြစ်ပါရေ။

**အကျိုးကျေးဇူး:**
- Code duplication လျော့ရေ
- Testing/bug fixing လွယ်ရေ
- Program structure ပိုရှင်းရေ

---

## Method Syntax

```java
accessModifier returnType methodName(parameters) {
    // body
    return value; // returnType != void ဖြစ်ကေ
}
```

---

## ၁) `void` Method

```java
public class Main {
    static void greet(String name) {
        System.out.println("Hi " + name);
    }

    public static void main(String[] args) {
        greet("Aung Aung");
        greet("Su Su");
    }
}
```

---

## ၂) Return Value Method

```java
public class Main {
    static int add(int a, int b) {
        return a + b;
    }

    static double average(int a, int b, int c) {
        return (a + b + c) / 3.0;
    }

    public static void main(String[] args) {
        int sum = add(10, 20);
        double avg = average(80, 90, 70);

        System.out.println("Sum = " + sum);
        System.out.println("Average = " + avg);
    }
}
```

---

## ၃) Parameters နန့် Arguments

- **Parameter** = method definition အထဲက variable
- **Argument** = method call လုပ်တေခါပီးရေ value

```java
static int multiply(int x, int y) { // x,y = parameters
    return x * y;
}

int result = multiply(3, 4); // 3,4 = arguments
```

---

## ၄) Method Overloading

နာမည်တူ method တိကို parameter type/number မတူအောင် ရီးလို့ရရေ။

```java
static int add(int a, int b) {
    return a + b;
}

static double add(double a, double b) {
    return a + b;
}

static int add(int a, int b, int c) {
    return a + b + c;
}
```

---

## ၅) Scope (Local vs Field)

```java
public class Main {
    static int count = 0; // field (class scope)

    static void increment() {
        int step = 1; // local scope
        count += step;
    }

    public static void main(String[] args) {
        increment();
        increment();
        System.out.println(count); // 2
    }
}
```

---

## Pass-by-Value ကို မှတ်ထားရန်

Java မှာ method parameter passing က pass-by-value ဖြစ်ပါရေ။
Primitive type ပို့ဖို့ဆိုကေ copy value ကို ပို့စွာဖြစ်လို့ original ကို မပြောင်းနိုင်ပါ။

```java
static void change(int x) {
    x = 100;
}

int a = 10;
change(a);
System.out.println(a); // 10
```

---

## အဖြစ်များရေ အမှားတိ

```java
static add(int a, int b) {   // return type မပါစွာ
    return a + b;
}

static void show() {
    return 5; // void method မှာ value return လို့မရပါ
}
```

---

## အခန်းချုပ်

- Method design က program quality ကို တိုးစီရေ
- Return type, parameters, scope ကို သီသီချာချာ နားလည်ထားရဖို့
- Reusable method တိရီးလီ code maintain လုပ်ရလွယ်လီဖြစ်တေ

---

## လေ့ကျင့်ခန်းတိ

1. `max(int a, int b)` method ရီးပါ
2. `isEven(int n)` boolean method ရီးပါ
3. Celsius -> Fahrenheit ပြောင်းရေ method ရီးပါ
4. Overloading နန့် `area()` method ကို rectangle/circle အတွက် ရီးပါ
