# အခန်း (၁၃) - File I/O Basics

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- Text file ထဲသို့ data write လုပ်နိုင်လာဖို့
- Text file က data read လုပ်နိုင်လာဖို့
- `try-with-resources` သုံးပြီး resource leak မဖြစ်အောင် ရီးနိုင်လာဖို့
- File not found / I/O errors ကို basic handle လုပ်နိုင်လာဖို့

---

## File I/O ဆိုစွာ ဇာလဲ?

File I/O = file system ထဲကဖိုင်တိကို read/write လုပ်စွာပါ။

- I = Input (ဖိုင်ကဖတ်)
- O = Output (ဖိုင်ထဲရီး)

Java မှာအများဆုံးစသုံးရေ classes:
- `File`
- `FileWriter`, `BufferedWriter`
- `FileReader`, `BufferedReader`

---

## ၁) File ထဲသို့ ရီးခြင်း (Write)

```java
import java.io.FileWriter;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        try (FileWriter fw = new FileWriter("notes.txt")) {
            fw.write("Hello File\n");
            fw.write("Java File I/O Basic\n");
            System.out.println("Write success");
        } catch (IOException e) {
            System.out.println("Write error: " + e.getMessage());
        }
    }
}
```

`try (...)` syntax က auto-close လုပ်ပီးရေ (manual `close()` မလို)။

---

## ၂) Append mode

Default `FileWriter("notes.txt")` က file အဟောင်းကို overwrite လုပ်ပါရေ။
append လုပ်ချင်ကေ 2nd parameter `true` ထည့်ပါ:

```java
FileWriter fw = new FileWriter("notes.txt", true);
```

---

## ၃) File က ဖတ်ခြင်း (Read)

```java
import java.io.BufferedReader;
import java.io.FileReader;
import java.io.IOException;

public class Main {
    public static void main(String[] args) {
        try (BufferedReader br = new BufferedReader(new FileReader("notes.txt"))) {
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
        } catch (IOException e) {
            System.out.println("Read error: " + e.getMessage());
        }
    }
}
```

---

## ၄) File exists စစ်ခြင်း

```java
import java.io.File;

File f = new File("notes.txt");
if (f.exists()) {
    System.out.println("File exists");
    System.out.println("Path: " + f.getAbsolutePath());
} else {
    System.out.println("File not found");
}
```

---

## ၅) Practical Example (Simple Log Writer)

```java
import java.io.FileWriter;
import java.io.IOException;
import java.time.LocalDateTime;

public class Main {
    public static void main(String[] args) {
        try (FileWriter fw = new FileWriter("app.log", true)) {
            fw.write("Program started: " + LocalDateTime.now() + "\n");
            System.out.println("Log saved");
        } catch (IOException e) {
            System.out.println("Log write failed: " + e.getMessage());
        }
    }
}
```

---

## အဖြစ်များရေ အမှားတိ

```java
FileWriter fw = new FileWriter("notes.txt");
fw.write("Hello");
// fw.close() မခေါ်ဘဲထားကေ data မပြည့်စုံဘဲ file ထဲမဝင်နိုင်
```

```java
new FileReader("not-exist.txt"); // FileNotFoundException
```

```java
while (br.readLine() != null) {
    System.out.println(br.readLine()); // line skip ဖြစ်တတ်
}
```

Correct pattern:

```java
String line;
while ((line = br.readLine()) != null) {
    System.out.println(line);
}
```

---

## အခန်းချုပ်

- File I/O က data persistence အတွက် core step ဖြစ်တေ
- `try-with-resources` သုံးကေ close မမေ့ဘဲ safe ဖြစ်ရေ
- Read/Write operations မှာ `IOException` handling ကို မဖြစ်မနေစဉ်းစားရေ

---

## လေ့ကျင့်ခန်းတိ

1. User name တိကို file ထဲ append လုပ်ပီးရေ program ရီးပါ
2. `students.txt` က line count ရှာပါ
3. `input.txt` ဖတ်ပြီး uppercase ပြောင်းပြီး `output.txt` ထဲရေးပါ
4. File မဟိကေ "Create first" message ပြပီး program မပျက်အောင် handle လုပ်ပါ
