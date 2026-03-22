# အခန်း (၁၂) - Collections အခြေခံ (`ArrayList`)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- `ArrayList` create/add/read/update/remove လုပ်နိုင်လာဖို့
- Array နန့် `ArrayList` ကွာခြားချက်ကို နားလည်လာဖို့
- Loop နန့် `ArrayList` traverse လုပ်နိုင်လာဖို့
- `Collections.sort()` နန့် basic list operations ကို သုံးနိုင်လာဖို့

---

## Array vs ArrayList

| Feature | Array | ArrayList |
| :--- | :--- | :--- |
| Size | Fixed | Dynamic (auto grow/shrink) |
| Data types | primitive + object | object type only (`Integer`, `String`...) |
| Utility methods | နည်း | add/remove/contains စတေ built-in methods များ |

---

## ၁) `ArrayList` တည်ဆောက်နည်း

```java
import java.util.ArrayList;

ArrayList<String> names = new ArrayList<>();
names.add("Aung");
names.add("Su");
names.add("Mg Mg");

System.out.println(names); // [Aung, Su, Mg Mg]
```

**မှတ်ချက်:** primitive `int` မသုံးဘဲ wrapper `Integer` သုံးပါ။

```java
ArrayList<Integer> marks = new ArrayList<>();
marks.add(80);
marks.add(95);
```

---

## ၂) Core Methods

```java
ArrayList<String> fruits = new ArrayList<>();
fruits.add("apple");
fruits.add("banana");
fruits.add("mango");

System.out.println(fruits.get(1));   // banana
fruits.set(1, "grape");              // update
fruits.remove("apple");              // remove by value
System.out.println(fruits.size());   // 2
System.out.println(fruits.contains("mango")); // true
```

---

## ၃) Traverse (Loop)

### `for` loop

```java
for (int i = 0; i < fruits.size(); i++) {
    System.out.println(fruits.get(i));
}
```

### `for-each` loop

```java
for (String f : fruits) {
    System.out.println(f);
}
```

---

## ၄) Sorting

```java
import java.util.ArrayList;
import java.util.Collections;

ArrayList<Integer> nums = new ArrayList<>();
nums.add(45);
nums.add(12);
nums.add(90);
nums.add(34);

Collections.sort(nums);
System.out.println(nums); // [12, 34, 45, 90]
```

Descending လုပ်ချင်ကေ:

```java
Collections.sort(nums, Collections.reverseOrder());
```

---

## ၅) List Interface (သိထားသင့်)

```java
import java.util.ArrayList;
import java.util.List;

List<String> cities = new ArrayList<>();
cities.add("Sittwe");
cities.add("Yangon");
```

Variable type ကို `List` သုံးထားကေ နောက်ပိုင်း implementation ပြောင်းလဲဖို့ လွယ်ပါရေ။

---

## အဖြစ်များရေ အမှားတိ

```java
ArrayList<int> list = new ArrayList<>(); // Error: primitive type မရ
ArrayList<Integer> list2 = new ArrayList<>(); // Correct
```

```java
ArrayList<String> l = new ArrayList<>();
l.add("A");
System.out.println(l.get(1)); // IndexOutOfBoundsException
```

```java
for (String s : l) {
    l.remove(s); // ConcurrentModificationException ဖြစ်နိုင်
}
```

---

## အခန်းချုပ်

- `ArrayList` က dynamic data handling အတွက် array ထက် အများကြီးအဆင်ပြေရေ
- `add/get/set/remove/size/contains` တိကို သိထားကေ list tasks အများစု ဖြေရှင်းနိုင်ရေ
- Generic type (`ArrayList<String>`) ကို မှန်ကန်စွာ သုံးပါ

---

## လေ့ကျင့်ခန်းတိ

1. Student names list တခုမှာ add/remove/search လုပ်ရေ program ရီးပါ
2. Integer list တခုထဲက average/max/min ရှာပါ
3. Product names list ကို ascending/descending sort လုပ်ပါ
4. `List<String>` type နန့် list တခုတည်ဆောက်ပြီး loops ၂ မျိုးနန့် print ထုတ်ပါ
