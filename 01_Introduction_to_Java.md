# အခန်း (၁) - Java မိတ်ဆက် (Introduction to Java)

---

## ဒေအခန်းပြီးကေ ဇာသိရဖို့လဲ?

ဒီအခန်းပြီးကေ -
- Java ဘာသာစကားဧ အဓိကအယူအဆကို ရှင်းရှင်းလင်းလင်း နားလည်လာဖို့
- `JDK`, `JRE`, `JVM` ရို့ဧ ကွာခြားချက်ကို ပြောပြနိုင်ဖို့
- Java program တခု ဇာပိုင် compile/run လုပ်လဲဆိုစွာ သိလာဖို့
- Java file တခုဧ အခြေခံ structure ကို ကိုယ်တိုင်ဖတ်ပြီးကေ နားလည်နိုင်ဖို့

---

## Java ဆိုစွာ ဇာလဲ?

Java ဆိုစွာ general-purpose programming language တခုဖြစ်ပြီးကေ backend, Android, enterprise systems, data processing စရေ နီရာတိမှာ အများကြီး အသုံးပြုကတ်တေ။

Java ဧ အဓိကအားသာချက်တခုက **Write Once, Run Anywhere (WORA)** ပါ။
ဆိုလိုစွာက source code တခုကို compile လုပ်ပြီးကေ bytecode ဖြစ်လာကေ JVM ဟိရေ OS မျိုးစုံမှာ run လို့ရပါရေ။

---

## JDK / JRE / JVM ကို လွယ်လွယ်ကူကူ မှတ်ကတ်မေ

| Term | Full Name | ဇာလုပ်ပီးလဲ |
| :--- | :--- | :--- |
| `JVM` | Java Virtual Machine | `.class` bytecode ကို run လုပ်ပီးရေ |
| `JRE` | Java Runtime Environment | Java program run ဖို့ လိုအပ်တေ runtime package |
| `JDK` | Java Development Kit | Java ရီးဖို့ + run ဖို့ tools အပြည့် (compiler ပါရေ) |

**Beginner အတိအတွက် မှတ်ချက်:** လေ့လာဖို့လူတိအတွက်က `JDK` တင်ထားကေ လုံလောက်တေ။

---

## Java Program အလုပ်လုပ်ပုံ

```text
Main.java (source code)
   ↓ javac compile
Main.class (bytecode)
   ↓ java command / IDE run
Output (console)
```

---

## Program Structure ကို ခွဲဖတ်ကြည့်ကတ်မေ

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

| Code | အဓိပ္ပါယ် |
| :--- | :--- |
| `public class Main` | `Main` ဆိုရေ class ဖန်တီးစွာ |
| `main(...)` | program စတင်ရေ entry point |
| `System.out.println(...)` | console ပေါ်မှာ text ထုတ်ပြစွာ |

---

## `print` နန့် `println` ကွာခြားချက်

```java
System.out.print("A");
System.out.print("B");
System.out.println("C");
System.out.println("D");
```

**Output:**
```text
ABCD
```

- `print` က newline မဆင်းပါ
- `println` က newline ဆင်းရေ

---

## Comments ရီးနည်း

```java
// single-line comment

/*
   multi-line comment
*/

/**
 * documentation comment (Javadoc)
 */
```

Comment တိက code ကို ရှင်းပြဖို့အတွက်ရာဖြစ်ပြီးကေ program run ရေခါ အလုပ်မလုပ်ပါ။

---

## အဖြစ်များရေ အမှားတိ

1. Semicolon `;` မထည့်စွာ
```java
System.out.println("Hello") // Error
```

2. Class name နန့် file name မတူစွာ
- `Main.java` အထဲမှာ `public class Main` ဖြစ်ရဖို့

3. Case-sensitive မသတိထားစွာ
- `System` မှန်, `system` မှား
- `main` မှန်, `Main` မဟုတ်

---

## အခန်းချုပ်

- Java ကို bytecode + JVM architecture ကြောင့် cross-platform သဘောနန့် သုံးနိုင်ရေ
- Java လေ့လာဖို့လူတိအတွက် JDK ကိုရာ install လုပ်ဖို့လိုရေ
- Program entry point က `main` method ဖြစ်တေ

---

## လေ့ကျင့်ခန်းတိ

1. `Main.java` တခုရီးပြီးကေ `Hello, Java` ကို ထုတ်ကြည့်ပါ
2. `print` နန့် `println` ကိုသုံးပြီးကေ output ကွာခြားချက်ကို စမ်းကြည့်ပါ
3. Code အထဲမှာ single-line comment နန့် multi-line comment ကို ထည့်ရီးကြည့်ပါ

---

## Mini Challenge

Console မှာ ကိုယ့်အကြောင်း ၃ ကြောင်း (နာမည်, မြို့, ရည်မှန်းချက်) ကို ထုတ်ပီးရေ program တခု ရီးကြည့်ပါ။
