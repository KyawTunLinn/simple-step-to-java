# အခန်း (၆) - Loops (for, while, do-while)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Repetition tasks တိကို loop နန့် တိုတိုရှင်းရှင်း ရီးနိုင်လာဖို့
- `for`, `while`, `do-while` ရို့ကို အခြီအနိန်ပေါ်မူတည်ပြီးကေ ရွီးသုံးနိုင်ဖို့
- `break`, `continue`, nested loop ကို နားလည်လာဖို့
- Infinite loop ပြဿနာကို ရှောင်နိုင်လာဖို့

---

## Loop ဇာဖြစ်လို့ လိုလဲ?

Loop မသုံးဘဲ 1 ကနီ 5 အထိ print လုပ်ဖို့ဆိုကေ code ထပ်ရီးရဖို့:

```java
System.out.println(1);
System.out.println(2);
System.out.println(3);
System.out.println(4);
System.out.println(5);
```

Loop သုံးကေ concise and maintainable ဖြစ်ပါရေ။

---

## ၁) `for` Loop

Loop count ကို ကြိုသိရေခါ `for` သုံးပါ။

```java
for (initialization; condition; update) {
    // code
}
```

```java
for (int i = 1; i <= 5; i++) {
    System.out.println("Number: " + i);
}
```

### Multiplication Table Example

```java
int n = 5;
for (int i = 1; i <= 10; i++) {
    System.out.println(n + " x " + i + " = " + (n * i));
}
```

---

## ၂) `while` Loop

Loop count ကို ကြိုမသိဘဲ condition true ဖြစ်နီသရွေ့ run လုပ်ချင်ကေ `while` သုံးပါ။

```java
int count = 1;
while (count <= 5) {
    System.out.println(count);
    count++;
}
```

### Sentinel Input Example (`0` ထည့်ကေ ရပ်ဖို့)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int sum = 0;

        while (true) {
            System.out.print("Enter No (0 to Break Program): ");
            int num = sc.nextInt();

            if (num == 0) {
                break;
            }
            sum += num;
        }

        System.out.println("Total: " + sum);
        sc.close();
    }
}
```

---

## ၃) `do-while` Loop

အနည်းဆုံး တကြိမ် run မဖြစ်မနီ လုပ်ချင်ရေခါ `do-while` သုံးပါ။

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 5);
```

---

## ၄) `break` နန့် `continue`

### `break`
Loop ကိုချက်ချင်း ရပ်တန့်စီရေ။

```java
for (int i = 1; i <= 10; i++) {
    if (i == 6) break;
    System.out.println(i);
}
```

### `continue`
လက်ဟိ iteration ကိုကျော်ပြီးကေ နောက်တခုပြန်စရေ။

```java
for (int i = 1; i <= 10; i++) {
    if (i % 2 == 0) continue;
    System.out.println(i); // odd only
}
```

---

## ၅) Nested Loop

```java
for (int row = 1; row <= 5; row++) {
    for (int col = 1; col <= row; col++) {
        System.out.print("* ");
    }
    System.out.println();
}
```

---

## Loop တမျိုးချင်း ဇာအချိန်သုံးဖို့လဲ?

| Loop | သင့်တော်ရေအချိန် |
| :--- | :--- |
| `for` | iteration count သိပြီးခါ |
| `while` | condition based, count မသီချာရေခါ |
| `do-while` | at least one execution လိုရေခါ |

---

## အဖြစ်များရေ အမှားတိ

```java
while (true) {
    System.out.println("endless");
    // break မဟိ
}

int i = 0;
while (i < 5) {
    System.out.println(i);
    // i++ မဟိ -> infinite loop
}
```

---

## အခန်းချုပ်

- Loop က repetition အလုပ်တိကို efficient လုပ်ပီးရေ
- Loop တိုင်းမှာ termination condition ကို မဖြစ်မနီ စဉ်းစားပါ
- `break`/`continue` ကို readability မပျက်အောင် သုံးပါ

---

## လေ့ကျင့်ခန်းတိ

1. `for` loop နန့် 1 မှ 100 ပေါင်းလဒ်ရှာပါ
2. `while` loop နန့် 2 ဧ powers (`1,2,4,8...`) ကို 10 ကြိမ်ထုတ်ပါ
3. Nested loop နန့် 9x9 multiplication table ထုတ်ပါ
4. User input အထဲက even numbers count လုပ်တေ program ရီးပါ
