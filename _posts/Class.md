---
title:  JAVA Class
tags:
  - Java
  - Tedi
---

1.클래스의 개념과 기초 용어

1-1.클래스의 개념

클래스는 데이터와 처리 동작들을 하나로 모아 놓은 것이다. 데이터를 필드라고 하고, 데이터를 처리하는 동작을 메소드라고 한다. 필드와 메소드는 클래스의 멤버라고 한다.

1-2.클래스의 정의

```java
class Book { //Book이라는 클래스 생성
    int price; //price라는 멤버 변수 생성
    int num;   //num이라는 멤버 변수 생성
    String title; //title이라는 멤버 변수 생성

    int sum(){ //sum이라는 메소드를 정의
        return price * num; //price와 num을 곱한 값을 반환
    } //메소드 정의가 끝났음을 뜻하는 닫는 중괄호
} //클래스 정의 완료를 뜻하는 닫는 중괄호
```

클래스는 클래스명 뒤에 중괄호로 정의가 시작된다. 우선 클래스에서 사용할 변수와 메소드, 즉 필드를 정의해주는데, 이 행위를 클래스를 정의한다고 한다.

1-3.오브젝트

1-3-1.개념

클래스는 그 자체에 값을 저장할 수 없다. 그래서 값을 저장할 수 있는 변수 같은 것을 만드는데, 이를 객체, 즉 오브젝트라고 한다. 언어의 종류 중 객체지향이라는 말은 여기서 나왔다.

1-3-2.만드는 방법

```java
class Book { //Book이라는 클래스 생성
    int price; //price라는 멤버 변수 생성
    int num;   //num이라는 멤버 변수 생성
    String title; //title이라는 멤버 변수 생성

    int sum(){ //sum이라는 메소드를 정의
        return price * num; //price와 num을 곱한 값을 반환
    } //메소드 정의가 끝났음을 뜻하는 닫는 중괄호
} //클래스 정의 완료를 뜻하는 닫는 중괄호

public static void main(String[] args) { //main메소드 생성
        Book HarryPotter = new Book();//HarryPotter라는 Book타입의 오브젝트 생성
				Book Tale = new Book(); //Tale라는 Book타입의 오브젝트 생성
}

```

오브젝트는 생성할 때 클래스명 오브젝트명 = new 클래스명(); 형태로 만든다. 이는 패키지에서 불러온 class(Scanner 등) 울 사용할 때 new를 붙이는 것과 같은 맥락이다. 오브젝트는 한 클래스에서 몇 개든 만들 수 있다. int타입의 변수를 무한히 많이 만들 수 있는 것과 비슷한 원리다.

2.필드

2-1.필드의 개념

필드는 클래스 안의 변수를 말한다. 클래스에 필드를 추가하기 위해서는

```java
class Book {//Book이라는 클래스 생성
    int price;//Price라는 멤버 변수 생성
}
```

와 같이 클래스를 정의할 때 일반적인 변수를 선언하는 것과 같이 중괄호 안에 넣어주면 된다. 이때 이것을 필드의 정의라고 한다.

2-2.필드의 참조와 대입

2-2-1.필드의 참조와 대입

```java
class Book {//Book이라는 클래스 생성
    int price = 9;//price라는 멤버 변수를 9로 초기화
		int total = price + 2;//total라는 멤버 변수를 price+2인 11로 초기화
}
```

같은 오브젝트 내에 필드에 값을 대입하려면 일반적으로 변수에 값을 대입하는 것과 같이 대입하면 된다. 참조도 마찬가지로 변수의 이름을 그대로 쓴다.

2-2-2. 다른 오브젝트의 필드의 참조와 대입

```java
class Book {//Book이라는 클래스 생성
    int price = 9;//price라는 멤버 변수를 9로 초기화
    int total = price + 2;//total이라는 멤버 변수를 price+2인 11로 초기화
}

public class BookShelf {//BookShelf라는 메인 메소드를 포함하는 클래스 생성
    public static void main(String[] args) {//메인 메소드 생성
        Book book1 = new Book();//book1이라는 Book타입의 클래스 생성
        book1.price = 3;//book1의 price를 3으로 초기화
        book1.total = 15;//book1의 total을 15로 초기화
        System.out.println(book1.price + book1.total); //book1의 price와 total을 더한 값인 18출력
    }
}
```

다른 오브젝트의 필드를 참조하거나 필드에 값을 대입하고 싶을 때는 오브젝트명.필드명 형태로 작성한 후 일반 변수와 똑같이 참조나 대입 연산을 실행한다.

3.메소드의 정의

3-1.메소드의 개념

메소드는 사용자가 준 값을 지시대로 처리해서 결과를 토해 내는 상자이다. 수학에서의 '함수'라고 생각하면 이해하기 쉽다. 메소드에 넣어주는 값을 인수, 즉 파라미터라고 하며  토해내는 결과 값을 리턴값, 즉 반환 값이라고 한다. 

```java
public int plus(int num1, int num2) {//setname이라는 메소드 선언
    return num1 + num2;//파라미터인 num1과 num2의 합 반환
}
   
```

이 예제에서는 setter를 이용해 cat이라는 객체의 이름에 boby를 대입했다. 꼭 getter, setter가 

3-2.클래스에서의 메소드 사용

클래스에서는 메소드를 클래스 안에 선언하는데, 이 메소드는 멤버 변수의 값을 변경하거나 가져올 수 있다. 대표적으로 getter와 setter가 있다.

```java
class Animal {// Animal 클래스 생성
    String name;//name이라는 멤버 변수 선언

    public void setName(String name) {//setname이라는 메소드 선언
        this.name = name;//name에 이 함수의 파라미터 대입
    }
}

public class Sample {//Sample이라는 클래스 생성
    public static void main(String[] args) {//main함수(프로그램의 시작점) 선언
        Animal cat = new Animal();//cat이라는 Animal타입의 객체 생성
				cat.setName("boby");  //setname 메소드 실행
        System.out.println(cat.name);//cat.name 출력
    }
}
```

4.생성자

4-1.생성자의 정의

생성자는 객체를 선언할 때 멤버 변수를 초기화하기 위해 존재한다. class에서 객체를 생성할 때 보통은 new 클래스명( ); 형태로 생성을 해 준다. 이는 사실 파라미터로 아무 것도 받지 않는 기본 생성자가 자동으로 제공된 것이다. 하지만 생성자를 따로 선언하게 되면 객체를 생성할 때 괄호 안에 생성자의 파라미터를 넣어야 한다. 대부분의 경우에는 생성자가 멤버 변수에 이 파라미터를 넣어준다.

```java
class Calculator {//calculator라는 클래스 선언
    int left, right;//left,right라는 멤버 변수 선언
 
    public Calculator(int left, int right) {//calculator의 생성자 선언(int 타입 파라미터 2개)
        this.left = left;//이 클래스의 left에 파라미터 left 대입
        this.right = right;//이 클래스의 right에 파라미터 right 대입
    }
 
    public void sum() {
        System.out.println(this.left + this.right);//left와 right의 합을 구하는 메소드
    }
 
    public void avg() {
        System.out.println((this.left + this.right) / 2);//left와 right의 평균을 구하는 메소드
    }
}
 
public class CalculatorDemo1 {//CalculatorDemo1라는 클래스 생성
 
    public static void main(String[] args) {//main함수 생성
 
        Calculator c1 = new Calculator(10, 20);//c1이라는 객체 생성(생성자로 left,right 입력)
        c1.sum();//c1에서 sum함수 작동
        c1.avg();//c1에서 avg함수 작동
 
        Calculator c2 = new Calculator(20, 40);//c2라는 객체 생성(생성자로 left,right 입력)
        c2.sum();//c2에서 sum함수 작동
        c2.avg();//c2에서 avg함수 작동
    }
 
}
```

여기서 Calculator 클래스의 생성자를 선언해 주었다. 여기서 알 수 있듯이 생성자는 클래스명과 이름이 동일한 메소드 형태로 만들면 된다. 이 생성자의 기능은 생성자에서 받은 파라미터 2개를 각각 멤버 변수에 넣어주는 것이다. 그래서 객체 c1,c2를 생성할 때 괄호에 생성자의 파라미터 2개를 넣어 준다. 이렇게 하면  멤버 변수에 일일이 값을 넣어줄 필요가 없기 때문에 매우 효율적이다.

4-2.생성자 오버로딩

우선 오버로딩이란 같은 클래스의 메소드를 재정의하는 것이다. 그러니까 이름이 같아도 파라미터의 개수나 타입이 다르면 허용된다는 것이다. 그러니 오버로딩을 하는 목적은 같은 기능을 사용하는 메소드를 하나의 이름으로 사용할 수 있는 것이다. 예를 들어, add라는 메소드가 있는 경우 파라미터에 int2개를 넣으면 두 개를 더한 값을 리턴해 주는 것이 일반적이다. 하지만 오버로딩으로 char타입 파라미터 2개를 받게 되면 두 문자를 합친 문자열을 리턴하게 할 수도 있는 것이다.

```java
public void print() {
		System.out.println("오버로딩1");
	}

	String print(Integer a) {
		System.out.println("오버로딩2");
		return a.toString();
	}

	void print(String a) {
		System.out.println("오버로딩3");
		System.out.println(a);
	}

	String print(Integer a, Integer b) {
		System.out.println("오버로딩4");
		return a.toString() + b.toString();
	}
```

이 예제에서 print의 파라미터가 없는  것, int타입 1개, String타입 1개, int타입 2개 총 4가지가 있다. 예를 들어 print(”hello”)로 하면 오버로딩3, hello가 출력되고, print(2, 3)을 하면 오버로딩4, 5가 출력된다.

마찬가지로 생성자도 일종의 메소드이므로 오버로딩할 수 있다. 이 경우 객체를 생성할 때 선택할 수 있는 가짓수가 늘어나게 된다.

```java
public class Student {
	
	public int studentID; //학번
	public String studentName; //이름
	public String address; //주소
	
	public Student(int id, String name) {
		studentID = id;
		studentName = name;
	}
	
	public Student(String name) {
		studentName = name;
	}
 }
```

이 경우 객체를 생성할 때 id와 name을 둘 다 괄호 안에 넣을 수도 있고 name만 넣을 수도 있다.

5.상속

상속이란 원래 부모가 자녀에게 부모의 유산을 물려 주는 것을 말한다. 클래스에서의 상속도 마찬가지로 부모 클래스가 자녀 클래스에게 멤버를 물려 줄 수 있다. 이때 자녀 클래스는 부모 클래스의 멤버를 사용할 수 있게 된다.

```java
public class ParentBook{
  String name; //필드
  int price;

public void Print(){ // 메소드
  System.out.println("책의 이름과 가격 : "+name+" "+price);
}
```

우선 ParentBook이라는 클래스를 하나 선언해준다.

```java
public class ChildBook extends ParentBook{
  ChildBook (String name, int price){ // 생성자
    this.name = name;  //  ChildBook이 ParetBook의 필드를 상속받아서 가능한 선언
    this.price = price; //  "
}
```

이때 ChildBook이라는 클래스는 extends를 이용해서 상속을 받을 수 있다. 여기서는 ChildBookㅢ 생성자를 이용해서 부모 클래스의 멤버들을 초기화시켰다. 하지만 모든 경우에 부모 클래스의 멤버에 마음대로 접근할 수 있는 것은 아니다.  부모 클래스의 멤버에 Private이 걸려 있으면 그 멤버는 상속받지 못한다. 

멤버뿐만 아니라 부모 클래스에서 생성자도 상속을 받을 수 있다. 이때 부모 클래스의 생성자에는 super을 써 주어야 한다. 

```java
public class ParentBook{
  String name; //필드
  int price;

  public ParentBook (String name, int price){ // 부모의 생성자가 있는 경우
    this.name = name;
    this.price = price;
}
  public void Print(){ // 메소드
    System.out.println("책의 이름과 가격 : "+name+" "+price);
}
```

여기서 부모 클래스의 생성자를 선언해 주었다.

```java
public class ChildBook extends ParentBook{
  ChildBook (){ // 자식 생성자
    super("나의 라임오렌지 나무", 10000); // 반드시 자식 생성자 첫줄에 선언
}
```

이때 자녀 클래스의 생성자에서 이를 사용하려면 반드시 자녀의 생성자의 첫줄에 super(파라미터)형태로 선언을 해 주어야 한다.