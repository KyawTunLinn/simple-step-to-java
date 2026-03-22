# အခန်း (၄) - Operators

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Arithmetic, comparison, logical operators ကို မှန်မှန်ကန်ကန် သုံးနိုင်လာဖို့
- `++` / `--` နန့် `+=` စတေ shorthand operators ကို နားလည်လာဖို့
- Ternary operator နန့် short decision ရီးနိုင်လာဖို့
- Integer division, `=` vs `==` လို common mistakes ကို ရှောင်နိုင်လာဖို့

---

## ၁) Arithmetic Operators

| Operator | Meaning | Example | Result |
| :---: | :--- | :---: | :---: |
| `+` | addition | `5 + 3` | `8` |
| `-` | subtraction | `5 - 3` | `2` |
| `*` | multiplication | `5 * 3` | `15` |
| `/` | division | `10 / 4` | `2` |
| `%` | modulus | `10 % 3` | `1` |

```java
int a = 10;
int b = 4;
System.out.println(a / b);        // 2
System.out.println((double)a / b); // 2.5
```

---

## ၂) Assignment Operators

| Operator | Expanded Form |
| :---: | :--- |
| `x += 3` | `x = x + 3` |
| `x -= 3` | `x = x - 3` |
| `x *= 3` | `x = x * 3` |
| `x /= 3` | `x = x / 3` |
| `x %= 3` | `x = x % 3` |

---

## ၃) Increment / Decrement

```java
int x = 5;
System.out.println(x++); // 5 (print ပြီးမှတိုးရေ)
System.out.println(x);   // 6

System.out.println(++x); // 7 (တိုးပြီးမှ print)
```

---

## ၄) Comparison Operators

| Operator | Meaning |
| :---: | :--- |
| `==` | equal |
| `!=` | not equal |
| `>` | greater than |
| `<` | less than |
| `>=` | greater or equal |
| `<=` | less or equal |

Comparison result က `boolean` (`true` / `false`) ဖြစ်ပါရေ။

---

## ၅) Logical Operators

| Operator | Meaning |
| :---: | :--- |
| `&&` | AND (နှစ်ခုလုံး true ဖြစ်ရဖို့) |
| `||` | OR (တခု true ကေရရေ) |
| `!` | NOT (true/false ပြောင်းရေ) |

```java
int age = 20;
boolean hasID = true;

System.out.println(age >= 18 && hasID); // true
System.out.println(age < 18 || hasID);  // true
System.out.println(!hasID);             // false
```

---

## ၆) Ternary Operator

```java
condition ? valueIfTrue : valueIfFalse;
```

```java
int score = 72;
String result = (score >= 50) ? "Pass" : "Fail";
System.out.println(result);
```

---

## Operator Precedence (အရေးကြီး)

များသောအားဖြင့် -
1. `()`
2. unary (`!`, `++`, `--`)
3. `*`, `/`, `%`
4. `+`, `-`
5. comparison (`>`, `<`, `>=`, `<=`)
6. equality (`==`, `!=`)
7. `&&`
8. `||`
9. assignment (`=`, `+=` ...)

ရှင်းချင်ကေ `()` ထည့်ရီးပါ။

---

## အဖြစ်များရေ အမှားတိ

```java
if (x = 5) { }   // Error: assignment
if (x == 5) { }  // Correct: comparison

int r = 7 / 2;       // 3
double d = 7 / 2;    // 3.0 (already int division)
double d2 = 7.0 / 2; // 3.5
```

---

## အခန်းချုပ်

- Operators တိက data ကိုတွက်ချက်/နှိုင်းယှဉ်/ဆုံးဖြတ်ဖို့ အခြေခံအင်ဂျင်ပါ
- Integer division နန့် `=`/`==` က beginner အတွက် အများဆုံးကြုံရ bug ဖြစ်တတ်တေ
- Complex expressions မှာ parentheses သုံးခြင်းက safer ဖြစ်တေ

---

## လေ့ကျင့်ခန်းတိ

1. BMI (`weight / (height * height)`) တွက်ပီးရေ program ရီးပါ
2. Score ကို ternary နန့် `Pass`/`Fail` သတ်မှတ်ပါ
3. `&&`, `||`, `!` သုံးပြီးကေ login rule တခု ရီးပါ
4. `x++` နန့် `++x` ကွာခြားချက်ကို output နန့်ပြပါ
