# အခန်း (၈) - Arrays

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Array declaration/initialization ကို မှန်မှန်ကန်ကန် ရီးနိုင်လာဖို့
- Array elements access/update/traverse လုပ်နိုင်လာဖို့
- 1D/2D arrays ကို loop နန့်ကိုင်တွယ်နိုင်လာဖို့
- `Arrays.sort`, `Arrays.equals`, `Arrays.toString` သုံးနိုင်လာဖို့

---

## Array ဆိုစွာ ဇာလဲ?

Array ဆိုစွာ data type တူရေ values တိကို index နံပါတ်နန့် အစုလိုက် သိမ်းထားနိုင်ရေ structure ဖြစ်ပါရေ။

```java
String[] students = {"Aung", "Su", "Mg", "Hnin", "Kyaw"};
```

**အရေးကြီး:** index က `0` ကနီစပါရေ။

---

## Array တည်ဆောက်နည်း ၂ မျိုး

### နည်း ၁: Direct initialization

```java
int[] scores = {85, 90, 78, 95, 88};
```

### နည်း ၂: Size ပီးပြီးနောက်မှထည့်ခြင်း

```java
int[] marks = new int[5];
marks[0] = 85;
marks[1] = 90;
```

---

## Access / Update / Length

```java
String[] fruits = {"mango", "apple", "banana"};

System.out.println(fruits[0]); // mango
fruits[1] = "grape";
System.out.println(fruits[1]); // grape
System.out.println(fruits.length); // 3
```

---

## Loop ဖြင့် Traverse

### `for` loop

```java
int[] scores = {85, 90, 78, 95, 88};
for (int i = 0; i < scores.length; i++) {
    System.out.println("scores[" + i + "] = " + scores[i]);
}
```

### `for-each` loop

```java
for (int score : scores) {
    System.out.println(score);
}
```

---

## Array လုပ်ဆောင်ချက်တိ

### Average

```java
int[] marks = {85, 90, 78, 95, 88};
int sum = 0;

for (int m : marks) {
    sum += m;
}

double avg = (double) sum / marks.length;
System.out.println("Average = " + avg);
```

### Max / Min

```java
int[] nums = {45, 12, 78, 34, 90, 23};
int max = nums[0];
int min = nums[0];

for (int n : nums) {
    if (n > max) max = n;
    if (n < min) min = n;
}

System.out.println("Max = " + max);
System.out.println("Min = " + min);
```

---

## 2D Array

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6},
    {7, 8, 9}
};

for (int i = 0; i < matrix.length; i++) {
    for (int j = 0; j < matrix[i].length; j++) {
        System.out.print(matrix[i][j] + " ");
    }
    System.out.println();
}
```

---

## `Arrays` Utility Class

```java
import java.util.Arrays;

int[] a = {5, 2, 8, 1, 9, 3};
Arrays.sort(a);
System.out.println(Arrays.toString(a)); // [1, 2, 3, 5, 8, 9]

int[] x = {1, 2, 3};
int[] y = {1, 2, 3};
System.out.println(Arrays.equals(x, y)); // true
```

---

## အဖြစ်များရေ အမှားတိ

```java
int[] arr = {1, 2, 3};
System.out.println(arr[3]); // ArrayIndexOutOfBoundsException

System.out.println(arr[1]); // second element (not first)
System.out.println(arr[0]); // first element

int[] p = {1, 2, 3};
int[] q = {1, 2, 3};
System.out.println(p == q);            // false (reference)
System.out.println(Arrays.equals(p,q)); // true (content)
```

---

## အခန်းချုပ်

- Array က same-type data ကို efficient စုစည်းပီးရေ
- Index `0` start ကို မမိပါနန့်
- Loop နန့် Arrays utility methods သိထားကေ data tasks အများစုကို ဖြေရှင်းနိုင်ရေ

---

## လေ့ကျင့်ခန်းတိ

1. Score array တခုကနီ average/max/min ရှာပါ
2. Array တခုကို sort လုပ်ပြီး ascending/descending ပြပါ
3. 3x3 matrix ကို print လုပ်ပြီးကေ diagonal sum ရှာပါ
4. Number တခု array အထဲမှာဟိ/မဟိ linear search ရီးပါ
