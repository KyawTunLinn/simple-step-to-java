# အခန်း (၁၄) - Final Practice Projects

---

## ရည်ရွယ်ချက်

ဒီ chapter က chapter ၁ မှ ၁၃ အထိ သင်ခရေအရာတိကို အသုံးချဖို့ design လုပ်ထားစွာပါ။

Project မလုပ်ဘဲ course ပြီးစွာထက် project တခုလုပ်ပြီးကေ skill တက်မှု အများကြီးကွာဟလားပါရေ။

ဒေအခန်းကို `၂ ဆင့်` လုပ်လို့ရအောင် design လုပ်ထားပါရေ:
- Core Version (Chapter 1-10)
- Level 2 Upgrade (Chapter 11-13)

---

## Project 1 - Student Grade Manager

### Core Requirement (Chapter 1-10)
- ကျောင်းသား ၅ ယောက်ဧ နာမည်, အမှတ်ကို array နန့် သိမ်းပါ
- Average, max, min တွက်ပါ
- Grade (A-F) သတ်မှတ်ဖို့ method သီးသန့်ရီးပါ
- Summary report ကို print ထုတ်ပါ

### အသုံးချရဖို့ Chapter (Core)
- Chapter 3, 4, 5, 6, 7, 8

### Level 2 Upgrade (Chapter 11-13)
- `Person` -> `Student` inheritance ထည့်ပါ
- Grade policy ကို overriding နန့် design လုပ်ပါ (`ExamStudent`, `ProjectStudent` ပိုင်)
- `Student[]` အစား `ArrayList<Student>` သုံးပါ
- Report output ကို `student_report.txt` ထဲ save လုပ်ပါ
- Program စတင်ချိန် `student_report.txt` မဟိ/ဟိ စစ်ပြီး feedback ပြပါ

### အသုံးချရဖို့ Chapter (Upgrade)
- Chapter 11, 12, 13

---

## Project 2 - ATM Console App (Basic)

### Core Requirement (Chapter 1-10)
- `balance` ကို variable အဖြစ်ထားပါ
- Menu (`switch`) နန့် 1) Check Balance 2) Deposit 3) Withdraw 4) Exit တည်ဆောက်ပါ
- Withdraw မှာ balance မလောက်ကေ error message ပြပါ
- Program ကို `do-while` နန့် run ထားပါ
- Invalid menu input (text) ကို `try-catch` (သို့) safe input pattern နန့် handle လုပ်ပါ

### အသုံးချရဖို့ Chapter (Core)
- Chapter 2, 4, 5, 6, 7, 9, 10

### Level 2 Upgrade (Chapter 11-13)
- `Account` parent class နန့် `SavingsAccount` / `CurrentAccount` child class တည်ဆောက်ပါ
- `withdraw()` behavior ကို overriding နန့် account type ပေါ်မူတည်ပြီးကေ ပြောင်းပါ
- Transaction history ကို `ArrayList<String>` (သို့) `ArrayList<Transaction>` နန့် သိမ်းပါ
- Exit လုပ်ချိန် transaction history ကို `atm_log.txt` ထဲ append လုပ်ပါ
- Program restart ချိန် previous logs ကိုဖတ်ပြီး last 5 records ပြပါ

### အသုံးချရဖို့ Chapter (Upgrade)
- Chapter 11, 12, 13

---

## Project 3 - Library Book Tracker

### Core Requirement (Chapter 1-10)
- `Book` class တည်ဆောက်ပါ (`title`, `author`, `isBorrowed`)
- Constructor နန့် object တည်ဆောက်ပါ
- `borrowBook()` / `returnBook()` methods ရီးပါ
- Book objects တိကို array အထဲမှာသိမ်းပြီးကေ loop နန့် list ထုတ်ပါ

### အသုံးချရဖို့ Chapter (Core)
- Chapter 7, 8, 9

### Level 2 Upgrade (Chapter 11-13)
- `Book` parent class နန့် `Novel`, `TextBook` child class တိရီးပါ
- `displayInfo()` ကို overriding နန့် category-specific info ပြပါ
- Book storage ကို array အစား `ArrayList<Book>` နန့်ပြောင်းပါ
- Book list ကို `library_data.txt` ထဲ save/load လုပ်ပါ
- "borrowed only" filter ကို list loop နန့်ထုတ်ပြပါ

### အသုံးချရဖို့ Chapter (Upgrade)
- Chapter 11, 12, 13

---

## Bonus Tasks (လိုချင်ကေ ထပ်လုပ်ပါ)

1. Input validation ထည့်ပါ (negative amount မရပါ)
2. `throw new IllegalArgumentException(...)` နန့် business rule check တခုထည့်ပါ
3. Methods ခွဲစည်းပြီးကေ `Main` ကို clean ဖြစ်အောင်လုပ်ပါ
4. Error message တိကို user-friendly ပြပါ
5. File save format ကို CSV style (`name,score,grade`) ပြောင်းပြီးကေ read-back parse လုပ်ပါ
6. Project တခုအတွက် UML class diagram အနည်းဆုံး ၁ ခု ဆွဲပါ


---

## Self-Check Checklist

- [ ] Program compile/run error မဟိ
- [ ] Variables/method names meaningful ဖြစ်တေ
- [ ] Repeated code ကို methods နန့်ခွဲထားရေ
- [ ] At least one array, one loop, one condition ပါဝင်ရေ
- [ ] At least one class/object (Project 2 or 3)
- [ ] At least one input error handling (`try-catch` or `hasNextInt`) ပါဝင်ရေ
- [ ] Inheritance + overriding အနည်းဆုံး တခုပေါင်းထည့်ထားရေ (Level 2)
- [ ] `ArrayList` နန့် data manage လုပ်ထားရေ (Level 2)
- [ ] File save/load feature အနည်းဆုံး တခုပေါင်းထည့်ထားရေ (Level 2)

---
