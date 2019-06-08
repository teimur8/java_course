
- Из за того что у нам строгая типизация, для удобства и что бы меньше писать кода добавлены генерики.
- генерики не может работать с простыми типами, поэтому добавлены алиасы с большой буквы.

Простой пример с генериком. Класс `Gen` принимает любой тип, и возвращает его.

```java
class Gen<T> {
    T ob; // объявление объекта типа T

    // Передать конструктору ссылку на объект типа T
    Gen(T o) {
        ob = o;
    }

    // Вернуть ob
    T getob() {
        return ob;
    }

    // Показать тип T
    void showType() {
        System.out.println("Тип T: " + ob.getClass().getName());
    }
}
class Scratch {
    public static void main(String[] args) {

        // Integer
        Gen<Integer> iOb;
        iOb = new Gen<Integer>(77);
        iOb.showType();
        int value = iOb.getob();
        System.out.println("Значение " + value);

        // String
        Gen<String> strOb = new Gen<String>("Обобщённый текст");
        strOb.showType();
        String str = strOb.getob();
        System.out.println("Значение: " + str);

        /*
        Тип T: java.lang.Integer
        Значение 77
        Тип T: java.lang.String
        Значение: Обобщённый текст
        */
    }
}
```


```java
ArrayList<String> mCatNames = new ArrayList<>();
private ArrayList<String> mCatNames = new ArrayList<String>();

MyClass<Integer, String> mcObj = new MyClass<Integer, String>(33, "Meow"); // старый способ в JDK 6
MyClass<Integer, String> mcObj = new MyClass<>(33, "Meow"); // новый способ в JDK 7

```

# Несколько параметров

```java
class TwoGen<T, V> {
    T ob1;
    V ob2;

    // Передать конструктору ссылки на объекты двух типов
    TwoGen(T o1, V o2) {
        ob1 = o1;
        ob2 = o2;
    }

    void showTypes() {
        System.out.println("Тип T: " + ob1.getClass().getName());
        System.out.println("Тип V: " + ob2.getClass().getName());
    }

    T getob1() {
        return ob1;
    }

    V getob2() {
        return ob2;
    }
}
class Scratch {
    public static void main(String[] args) {

        // Используем созданный класс
        TwoGen<Integer, String> twogenObj = new TwoGen<Integer, String>(77, "Обобщённый текст");

        // Узнаем типы
        twogenObj.showTypes();

        // Узнаем значения
        int value = twogenObj.getob1();
        System.out.println("Значение: " + value);

        String str = twogenObj.getob2();
        System.out.println("Значение: " + str);

        /*
        Тип T: java.lang.Integer
        Тип V: java.lang.String
        Значение: 77
        Значение: Обобщённый текст
         */

    }
}
```