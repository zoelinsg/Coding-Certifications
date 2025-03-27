# HackerRank Java
## Java8 解法 Part 1

- [Welcome to Java](https://www.hackerrank.com/challenges/welcome-to-java/problem?isFullScreen=true)

```java
public class Solution {

    public static void main(String[] args) {
        System.out.println("Hello, World.");
        System.out.println("Hello, Java.");
    }
}
```

- [Java Stdin and Stdout 1](https://www.hackerrank.com/challenges/java-stdin-and-stdout-1/problem?isFullScreen=true)

```java
import java.util.*;

public class Solution {

    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int a = scan.nextInt();
        int b = scan.nextInt();
        int c = scan.nextInt();
        
        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
    }
}
```

- [java-stdin-stdout](https://www.hackerrank.com/challenges/java-stdin-stdout/problem?isFullScreen=true)

```java
import java.util.Scanner;

public class Solution {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);
        int i = scan.nextInt();
        double d = scan.nextDouble();

        scan.nextLine();
        String s = scan.nextLine();
        
        System.out.println("String: " + s);
        System.out.println("Double: " + d);
        System.out.println("Int: " + i);
    }
}
```