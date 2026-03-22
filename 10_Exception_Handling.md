# အခန်း (၁၀) - Exception Handling (`try-catch`, `throw`, `throws`, `finally`)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Program crash မဖြစ်အောင် error ကို handle လုပ်နိုင်လာဖို့
- `try-catch-finally` ကို မှန်ကန်စွာ သုံးနိုင်လာဖို့
- `throw` နန့် `throws` ကွာခြားချက်ကို နားလည်လာဖို့
- Beginner မှာ မကြာခဏကြုံရေ exception တိကို ဖတ်ပြီး ဖြေရှင်းနိုင်လာဖို့

---

## Exception ဆိုစွာ ဇာလဲ?

Program run နီချိန် unexpected error တခုဖြစ်လာကေ Java က exception throw လုပ်ပါရေ။
Exception ကို မကိုင်တွယ်ကေ program ရပ်နိုင်ပါရေ။

ဥပမာ:
- `ArithmeticException` (`10 / 0`)
- `ArrayIndexOutOfBoundsException`
- `NullPointerException`
- `InputMismatchException`
- `NumberFormatException`

---

## ၁) `try-catch` Basic

```java
public class Main {
    public static void main(String[] args) {
        try {
            int result = 10 / 0;
            System.out.println(result);
        } catch (ArithmeticException e) {
            System.out.println("0 နန့်မစားလို့မရပါ: " + e.getMessage());
        }

        System.out.println("Program continues...");
    }
}
```

`try` အထဲမှာ error ဖြစ်နိုင်ရေ code ရီးပါ။
error ဖြစ်လာကေ matching `catch` block က run လုပ်ပါရေ။

---

## ၂) Multiple `catch`

```java
try {
    String text = null;
    System.out.println(text.length());
} catch (NullPointerException e) {
    System.out.println("Null value ကိုသုံးထားရေ");
} catch (Exception e) {
    System.out.println("Other error: " + e.getMessage());
}
```

**Rule:** specific exception ကို အပေါ်မှာ, generic `Exception` ကို အောက်မှာထားပါ။

---

## ၃) `finally`

`finally` block က exception ဖြစ်ဖြစ်/မဖြစ်ဖြစ် run ပါရေ။
cleanup (resource close) အတွက်သုံးရေ။

```java
try {
    System.out.println("Open resource");
    int x = 100 / 5;
    System.out.println(x);
} catch (Exception e) {
    System.out.println("Error");
} finally {
    System.out.println("Always run: cleanup");
}
```

---

## ၄) `throw` (ကိုယ်တိုင် Exception ပစ်ခြင်း)

Business rule မကိုက်ကေ ကိုယ်တိုင် exception throw လုပ်လို့ရရေ။

```java
static void withdraw(double amount) {
    if (amount <= 0) {
        throw new IllegalArgumentException("Amount must be > 0");
    }
    System.out.println("Withdraw success: " + amount);
}
```

---

## ၅) `throws` (Method signature မှာ ကြိုပြောခြင်း)

Method တခုက checked exception ပစ်နိုင်ရေဆိုစွာကို `throws` နန့် ကြိုပြောပါ။

```java
import java.io.IOException;

static void readFile() throws IOException {
    throw new IOException("File read failed");
}
```

Caller ဘက်မှာ `try-catch` လုပ်မလား, ထပ် `throws` ဆက်လှမ်းမလား ရွီးချယ်ရပါရေ။

---

## ၆) Checked vs Unchecked (Beginner မှတ်ရန်)

| Type | ဥပမာ | Handle မလုပ်ကေ compile error လား? |
| :--- | :--- | :--- |
| Checked Exception | `IOException`, `SQLException` | Yes |
| Unchecked Exception | `ArithmeticException`, `NullPointerException` | No |

---

## ၇) Input Handling Real Example (`Scanner` + `try-catch`)

```java
import java.util.InputMismatchException;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        try {
            System.out.print("Enter age: ");
            int age = sc.nextInt();
            System.out.println("Age = " + age);
        } catch (InputMismatchException e) {
            System.out.println("Number မဟုတ်ရေ input ထည့်ထားရေ");
        } finally {
            sc.close();
        }
    }
}
```

---

## Best Practices (Beginner Friendly)

1. `catch (Exception e)` တခုပဲ မသုံးဘဲ possible specific exceptions ကို ဦးစားပီးပါ
2. User ကို ဖတ်လို့ရရေ message ပြပါ (`Invalid amount`, `Try again`)
3. Error ကို မဖျောက်ပါနန့် (`catch` ထဲမှာ ဘာမှမလုပ်ဘဲမထားပါနန့်)
4. Normal flow control အတွက် exception ကို မသုံးပါနန့်

---

## အဖြစ်များရေ အမှားတိ

```java
try {
    int x = 10 / 0;
}
System.out.println("Hello"); // catch/finally မပါလို့ compile error
```

```java
catch (Exception e) { }
// error ကို silent လုပ်ထားလို့ debug ခက်ပါရေ
```

```java
catch (Exception e) {
    System.out.println("Error");
}
catch (ArithmeticException e) { } // generic catch နောက်မှာ specific catch ထားလို့မရ
```

---

## အခန်းချုပ်

- Exception handling က robust program ရီးဖို့ core skill ဖြစ်တေ
- `try-catch-finally` နန့် crash မဖြစ်အောင် control လုပ်နိုင်ရေ
- `throw` = ကိုယ်တိုင်ပစ်, `throws` = method contract
- Project တိမှာ input validation + exception handling ထည့်ကေ quality တက်လားပါရေ

---

## လေ့ကျင့်ခန်းတိ

1. User က number ၂ ခု ထည့်ခရေအခါ division လုပ်ပြီး `divide by zero` ကို `try-catch` နန့် handle လုပ်ပါ
2. `age < 0` ဆိုကေ `IllegalArgumentException` throw လုပ်ရေ method ရီးပါ
3. `String` တခုကို number ပြောင်းရာမှာ `NumberFormatException` ကို handle လုပ်ပါ
4. Mini ATM app မှာ invalid menu input (`text`) ကို `try-catch` နန့် handle လုပ်ပါ
