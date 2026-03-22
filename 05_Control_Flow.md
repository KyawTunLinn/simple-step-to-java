# အခန်း (၅) - Control Flow (If-Else, Switch)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Condition အပေါ်မူတည်ပြီးကေ code လမ်းကြောင်း ရွီးနိုင်လာဖို့
- `if`, `if-else`, `else-if`, nested if ကို အသုံးချနိုင်လာဖို့
- `switch` ဖြင့် menu-style logic ရီးနိုင်လာဖို့
- String comparison, missing `break` စရေ mistakes ကို ရှောင်နိုင်လာဖို့

---

## ၁) `if` Statement

```java
if (condition) {
    // condition true ဖြစ်ကေ run ပါဖို့
}
```

```java
int temperature = 35;
if (temperature > 30) {
    System.out.println("Drink more water");
}
```

---

## ၂) `if-else`

```java
int balance = 5000;
int withdraw = 3000;

if (withdraw <= balance) {
    System.out.println("ငွေထုတ်လို့ရရေ");
} else {
    System.out.println("ငွေမလောက်ပါ");
}
```

---

## ၃) `else-if` Chain

```java
int marks = 78;

if (marks >= 80) {
    System.out.println("Grade A");
} else if (marks >= 70) {
    System.out.println("Grade B");
} else if (marks >= 60) {
    System.out.println("Grade C");
} else if (marks >= 50) {
    System.out.println("Grade D");
} else {
    System.out.println("Grade F");
}
```

---

## ၄) Nested `if`

```java
boolean isRegistered = true;
String password = "1234";

if (isRegistered) {
    if (password.equals("1234")) {
        System.out.println("Login success");
    } else {
        System.out.println("Wrong password");
    }
} else {
    System.out.println("Please register first");
}
```

---

## ၅) `switch` Statement

```java
int day = 2;

switch (day) {
    case 1:
        System.out.println("Monday");
        break;
    case 2:
        System.out.println("Tuesday");
        break;
    case 3:
        System.out.println("Wednesday");
        break;
    default:
        System.out.println("Invalid day");
}
```

### String switch example

```java
String role = "admin";

switch (role) {
    case "admin":
        System.out.println("Full access");
        break;
    case "editor":
        System.out.println("Edit access");
        break;
    case "viewer":
        System.out.println("Read-only access");
        break;
    default:
        System.out.println("Unknown role");
}
```

---

## `if` vs `switch` ဇာအချိန်သုံးဖို့လဲ?

- Condition range (`>=`, `<=`, `&&`) များပြီးဆိုကေ `if-else`
- Value တခုကို case အများနန့်ရွီးစွာဆိုကေ `switch`

---

## အဖြစ်များရေ အမှားတိ

```java
if (x = 10) { }    // Error
if (x == 10) { }   // Correct

if (name == "Mg Mg") { }        // Bad for String content
if (name.equals("Mg Mg")) { }   // Correct

switch (day) {
    case 1:
        System.out.println("Mon");
    case 2:
        System.out.println("Tue"); // break မပါလို့ ဆက်ဝင်ဖို့
}
```

---

## အခန်းချုပ်

- Control Flow က program logic ဧ heart ဖြစ်တေ
- `if` family က condition-based decisions အတွက်သင့်တော်ရေ
- `switch` က discrete choices (menu, command, status) အတွက်သင့်တော်ရေ

---

## လေ့ကျင့်ခန်းတိ

1. Score (0-100) ကို grade (A-F) သတ်မှတ်ပါ
2. Weekday number (1-7) ကို day name ပြဖို့ `switch` သုံးပါ
3. Number တခု even/odd စစ်ဖို့ `if` သုံးပါ
4. Username/password mini login logic တခု ရီးပါ
