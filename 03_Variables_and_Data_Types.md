# အခန်း (၃) - Variables နန့် Data Types

---

## ဒေအခန်းပြီးကေ ဇာသိရဖို့လဲ?

- Variable ဆိုစွာ ဇာလဲ, ဇာပိုင် declare/init လုပ်ဖို့လဲ
- Primitive data types ၈ မျိုးကို ဇာအချိန် သုံးဖို့လဲ
- `String` ကို beginner အဆင့်မှာ မဖြစ်မနီသိရဖို့ operations တိ သုံးနိုင်လာဖို့
- Type casting (`widening`, `narrowing`) ကို နားလည်လာဖို့
- `final` constant နန့် naming rules ကို မှန်မှန်ကန်ကန် သုံးနိုင်လာဖို့

---

## Variable ဆိုစွာ ဇာလဲ?

Variable ဆိုစွာ data value တခုကို name တခုပီးပြီးကေ memory အထဲမှာ သိမ်းထားရေ နီရာဖြစ်ပါရေ။

```java
int age = 20;
// int = data type
// age = variable name
// 20 = value
```

---

## Variable ကြေညာပုံ

```java
DataType variableName = value;
```

**ဥပမာ:**

```java
int age = 25;
double salary = 500000.50;
char grade = 'A';
boolean passed = true;
String name = "Mg Mg";
```

---

## Data Types အမျိုးအစား ၂ မျိုး

1. Primitive data types
2. Non-primitive data types

### Primitive Data Types (၈ မျိုး)

| Type | Size | အသုံးပြုဖို့အခြေအနေ | ဥပမာ |
| :--- | :--- | :--- | :--- |
| `byte` | 8-bit | very small integer | `byte b = 100;` |
| `short` | 16-bit | small integer | `short s = 30000;` |
| `int` | 32-bit | normal integer | `int count = 1000;` |
| `long` | 64-bit | very large integer | `long pop = 8000000000L;` |
| `float` | 32-bit | decimal (less precision) | `float f = 3.14f;` |
| `double` | 64-bit | decimal (default choice) | `double d = 3.14159;` |
| `char` | 16-bit | single Unicode character | `char c = 'A';` |
| `boolean` | JVM-dependent | true/false state | `boolean ok = true;` |

**မှတ်ချက်:**
- `long` value နောက်မှာ `L` ကိုထည့်ပါ
- `float` value နောက်မှာ `f` ကိုထည့်ပါ

### Non-Primitive Data Types

```java
String city = "Yangon";
int[] numbers = {1, 2, 3};
```

---

## String Basics (Beginner Must-Know)

`String` က non-primitive type ဖြစ်ပြီးကေ text data သိမ်းဖို့အဓိကသုံးရေ။

```java
String name = "Aung Aung";
System.out.println(name.length());          // 9
System.out.println(name.toUpperCase());     // AUNG AUNG
System.out.println(name.substring(0, 4));   // Aung
```

### `==` နန့် `.equals()` ကွာခြားချက်

```java
String a = "java";
String b = new String("java");

System.out.println(a == b);        // false (reference compare)
System.out.println(a.equals(b));   // true  (content compare)
```

String content နှိုင်းယှဉ်ဖို့ `.equals()` (သို့) `.equalsIgnoreCase()` ကိုသုံးပါ။

---

## Type Casting

### Widening Casting (Automatic)

အသေး type ကနီ အကြီး type ကို ပြောင်းရေခါ Java က အလိုအလျောက် ပြောင်းပီးပါရေ။

```text
byte -> short -> int -> long -> float -> double
```

```java
int x = 100;
double y = x; // 100.0
```

### Narrowing Casting (Manual)

အကြီး type ကနီ အငယ် type သို့ ပြောင်းကေ manual cast လုပ်ဖို့လိုပါရေ။

```java
double price = 9.78;
int whole = (int) price; // 9 (decimal ပိုင်းပျောက်ရေ)
```

---

## Constants (`final`)

မပြောင်းချင်ရေ value တိကို `final` နန့် ကြေညာပါ။

```java
final double PI = 3.14159;
// PI = 4.0; // Error
```

---

## Naming Rules

### မှန်ကန်ရေပုံစံ
- `camelCase` ကိုသုံးပါ (`studentAge`, `totalMarks`)
- variable name ကို letter (သို့) `_` နန့်စပါ
- meaningful name ပီးပါ (`a`, `b` ထက် `totalPrice` က ပိုကောင်းရေ)

### မှားယွင်းရေပုံစံ

```java
int 1number = 5;   // number နန့် မစရပါ
int my-age = 10;   // - မသုံးရပါ
int class = 3;     // keyword ကို မသုံးရပါ
```

---

## Complete Example

```java
public class Main {
    public static void main(String[] args) {
        String studentName = "Ma Ma";
        int age = 18;
        double gpa = 3.85;
        boolean graduated = false;
        final String SCHOOL = "No.1 University";

        System.out.println("Name: " + studentName);
        System.out.println("Age: " + age);
        System.out.println("GPA: " + gpa);
        System.out.println("Graduated: " + graduated);
        System.out.println("School: " + SCHOOL);
    }
}
```

---

## အဖြစ်များရေ အမှားတိ

```java
long n = 15000000000;   // Error (L မပါစွာ)
long n2 = 15000000000L; // Correct

float p = 5.99;   // Error (f မပါစွာ)
float p2 = 5.99f; // Correct

char letter = "A"; // Error
char letter2 = 'A'; // Correct
```

---

## အခန်းချုပ်

- Variable = named memory location
- Primitive data types ၈ မျိုးကို အခြေအနေပေါ်မူတည်ပြီးကေ ရွီးသုံးရရေ
- `String` methods (`length`, `substring`, `equals`) ကို သိကေ text handling ပိုလွယ်ရေ
- Casting လုပ်ရေခါ data loss ဖြစ်နိုင်ချက်ကို သတိထားရဖို့
- `final` constant နန့် naming rules သုံးခြင်းက code quality ကို တိုးစီရေ

---

## လေ့ကျင့်ခန်းတိ

1. မိမိ profile အတွက် variables ၅ မျိုးတည်ဆောက်ပြီးကေ print ထုတ်ပါ
2. `double` ကို `int` cast လုပ်ပြီး result ကို မှတ်သားပါ
3. `final` variable တခုကို ပြောင်းကြည့်ပြီးကေ error ကိုလေ့လာပါ
4. `String` ၂ ခုကို `.equals()` နန့် နှိုင်းယှဉ်ပြီး output ပြပါ
5. Wrong naming ၃ ခုကိုရီးပြီးကေ correct version ပြန်ရီးပါ
