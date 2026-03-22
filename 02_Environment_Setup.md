# အခန်း (၂) - Environment ပြင်ဆင်ခြင်း (Environment Setup)

---

## ဒေအခန်းပြီးကေ ဇာလုပ်နိုင်ဖို့လဲ?

- JDK ကို system မှ install လုပ်နိုင်လာဖို့
- IDE (VS Code) မှာ Java project စတင်နိုင်ဖို့
- Terminal မှတဆင့် compile/run လုပ်နိုင်ဖို့
- `Scanner` နန့် user input ကို ဖတ်နိုင်ဖို့
- Invalid input ဖြစ်လာခါ program မပျက်စီဘဲ handle လုပ်နိုင်ဖို့

---

## ၁) JDK Install

Java လေ့လာဖို့လူတိအတွက် **LTS version** တခုကို ရွီးချယ်သင့်ပါရေ (ဥပမာ `17`, `21`, `25` ရို့ပိုင် LTS lines တိ)။

### Download Links
- Adoptium: <https://adoptium.net/>
- Oracle JDK: <https://www.oracle.com/java/technologies/downloads/>

### Install ပြီးကေ စစ်ဖို့ command

```bash
java -version
javac -version
```

Output ထွက်လာကေ installation အောင်မြင်ပါရေ။

---

## ၂) IDE ရွီးချယ်ခြင်း

| IDE | အထူးအားသာချက် |
| :--- | :--- |
| VS Code + Java Extensions | ပေါ့ပါးရေ၊ customize လုပ်ဖို့လွယ်ရေ |


ဒေ course မှာ VS Code ကိုသုံးပြီးကေ လေ့ကျင့်ကေ အဆင်ပြေပါရေ။

---

## ၃) ပထမဆုံး Program (IDE နန့်)

`Main.java`

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello from Java!");
    }
}
```

Run button ကိုနှိပ်ပြီးကေ output ကိုစစ်ပါ။

---

## ၄) Terminal နန့် Compile / Run (အရေးကြီး)

`Main.java` ဖိုင်တည်နီရာမှာ terminal ဖွင့်ပြီးကေ:

```bash
javac Main.java
java Main
```

ဒီ skill ကို သိထားကေ IDE မဟိရေ environment တိမှာလေ့ အလုပ်လုပ်နိုင်ပါရေ။

---

## ၅) User Input ဖတ်ခြင်း (`Scanner`)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        System.out.print("Your Name: ");
        String name = sc.nextLine();

        System.out.print("Your Age: ");
        int age = sc.nextInt();

        System.out.println("Hello " + name + " (" + age + " years old)");
        sc.close();
    }
}
```

---

## ၆) `Scanner` Beginner Trap ၂ ခု

### Trap (A): `nextInt()` နောက်မှာ `nextLine()` ချက်ချင်းဖတ်ရေပြဿနာ

`nextInt()` က newline (`\n`) ကို buffer ထဲမှာကျန်ထားပါရေ။
ဒါကြောင့် `nextLine()` ကိုချက်ချင်းခေါ်ကေ empty string ရနိုင်ပါရေ။

```java
System.out.print("Age: ");
int age = sc.nextInt();
sc.nextLine(); // leftover newline စားထုတ်

System.out.print("Address: ");
String address = sc.nextLine();
```

### Trap (B): Number နီရာမှာ text ထည့်စွာ

`nextInt()` input မှာ `abc` ပိုင် text ထည့်ခကေ `InputMismatchException` ဖြစ်နိုင်ပါရေ။

```java
import java.util.InputMismatchException;

try {
    System.out.print("Enter Age: ");
    int age = sc.nextInt();
    System.out.println("Age = " + age);
} catch (InputMismatchException e) {
    System.out.println("Plz enter no in age");
}
```

---

## ၇) Safe Input Utility Pattern (Beginner Friendly)

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int age;

        while (true) {
            System.out.print("Enter age: ");
            if (sc.hasNextInt()) {
                age = sc.nextInt();
                break;
            } else {
                System.out.println("Invalid input. Number ထည့်ပါ။");
                sc.next(); // invalid token ကျော်
            }
        }

        System.out.println("Your age: " + age);
        sc.close();
    }
}
```

---

## Common Setup Problems နန့် ဖြေရှင်းနည်း

| ပြဿနာ | ဖြစ်နိုင်ခြေ | ဖြေရှင်းနည်း |
| :--- | :--- | :--- |
| `'java' is not recognized` | PATH မချိတ်ထားစွာ | JDK reinstall ပြန်လုပ် + PATH စစ် |
| `javac: command not found` | JRE ကိုရာတင်ထားစွာ | JDK install လုပ်ပါ |
| `ClassNotFoundException` | folder/path မမှန်စွာ | command run ရေ directory (folder) ကိုစစ်ပါ |


---

## အခန်းချုပ်

- Java development အတွက် JDK လိုအပ်တေ
- IDE ဟိကေ productivity ကောင်းကေလေ့ terminal workflow ကိုလေ့ သင်ထားသင့်ရေ
- `Scanner` နန့် user input စပြီးကေ ဖတ်နိုင်ရေ

---

## လေ့ကျင့်ခန်းတိ

1. `java -version` နန့် `javac -version` run ပြီးကေ screenshot/reference သိမ်းထားပါ
2. IDE နန့် `Hello` program ကို run ပါ
3. Terminal နန့် `javac` + `java` ကို run ပါ
4. User နာမည်/အသက် input ယူပြီးကေ greeting ပြရေ program ရီးကြည့်ပါ
