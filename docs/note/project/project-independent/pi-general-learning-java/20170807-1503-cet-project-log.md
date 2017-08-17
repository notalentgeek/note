* `public static void main (String args []) {}` is a static function hence it cannot take value outside its scope.
* Here is a general Java programming skeleton.

```markdown
package something;

public class Main {
    public static void main (String args[]) {
        // Codes go here!
    }
}
```

* What if I have multiple `public static void main (String args[]) {}`?
    * This will depend on the entry point that will be compiled into.
    * For example if there are 2 `public static void main (String args[]) {}` in Eclipse, whichever file open as on the main window will be compiled.
* Here is an example article on how to make doubleton in Java, [http://ranksheet.com/Solutions/kb-Core-Java/1491_How-to-create-singleton-and-Doubleton-class-in-javaquestion-.aspx](http://ranksheet.com/Solutions/kb-Core-Java/1491_How-to-create-singleton-and-Doubleton-class-in-javaquestion-.aspx).
* Example codes for Main.java.

```markdown
package doubleton;

public class Main {
    public static void main (String args[]) {
        // Create `Doubleton` via public function `getDoubleton()`.
        Doubleton d1 = Doubleton.getDoubleton();
        Doubleton d2 = Doubleton.getDoubleton();
        // Should have the same hash code as `d2`.
        Doubleton d3 = Doubleton.getDoubleton();
        System.out.println(d1.hashCode());
        System.out.println(d2.hashCode());
        System.out.println(d3.hashCode());
    }
}
```

* Example codes for Doubleton.java.

```markdown
package doubleton;

class Doubleton {
    private static int initMax = 2;
    private static Doubleton doubleton[] = new Doubleton[initMax];

    // Private constructor, so the class cannot be created from outside the
    // class itself.
    private Doubleton () {}

    public static Doubleton getDoubleton () {
        if (doubleton[0] == null) {
            doubleton[0] = new Doubleton();
            return doubleton[0];
        }
        else if (doubleton[1] == null) {
            doubleton[1] = new Doubleton();
            return doubleton[1];
        }
        else {
            return doubleton[doubleton.length - 1];
        }
    }
}
```

* With this codes actually I can make anyton class for Java as well.
* Java example anyton for Main.java.

```markdown
package anyton;

public class Main {
    public static void main (String args[]) {
        Anyton a1 = Anyton.getAnyton();
        Anyton a2 = Anyton.getAnyton();
        Anyton a3 = Anyton.getAnyton();
        Anyton a4 = Anyton.getAnyton();
        Anyton a5 = Anyton.getAnyton();
        Anyton a6 = Anyton.getAnyton(); // This must be the same with `a5`.

        // Test!
        System.out.println(a1);
        System.out.println(a2);
        System.out.println(a3);
        System.out.println(a4);
        System.out.println(a5);
        System.out.println(a6);
        System.out.println(a5 == a6); // This should return `true`.
    }
}
```

* Anyton.java.

```markdown
package anyton;

public class Anyton {
    // For this test, I tried to create 5 anytons.
    private static int initCount = 5;
    private static Anyton[] anyton = new Anyton[initCount];

    private Anyton () {}

    public static Anyton getAnyton () {
        for (int i = 0; i < initCount; i ++) {
            if (anyton[i] == null) {
                anyton[i] = new Anyton();
                return anyton[i];
            }
        }

        return anyton[initCount - 1];
    }
}
```