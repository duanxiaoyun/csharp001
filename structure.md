# 结构体
  
在 C# 中，结构体是一种值数据类型。包含数据成员和方法成员。 **struct** 关键字是用于创建一个结构体。

结构体是用来代表一个记录。假设你想追踪一个图书馆的书。你可能想追踪每本书的属性如下：
  
- 标题
- 作者  
- 类别   
- 书号
  
## 定义一个结构体
  
定义一个结构体，你必须要声明这个结构体。结构体声明定义了一种新的数据类型，这个数据类型为你的程序包含了一个以上的成员变量。

例如，你可以声明一个书的结构如下：
  
<pre><code>struct Books
{
   public string title;
   public string author;
   public string subject;
   public int book_id;
};  
</code></pre>
  
下面的程序显示了结构体的用法：
  
<pre><code>using System;
struct Books
{
   public string title;
   public string author;
   public string subject;
   public int book_id;
};  

public class testStructure
{
   public static void Main(string[] args)
   {

      Books Book1;   /* 将 Book1 声明为 Book 类型  */
      Books Book2;   /* 将 Book2 声明为 Book 类型 */

      /* book 1 specification */
      Book1.title = "C Programming";
      Book1.author = "Nuha Ali"; 
      Book1.subject = "C Programming Tutorial";
      Book1.book_id = 6495407;

      /* book 2 详细数据 */
      Book2.title = "Telecom Billing";
      Book2.author = "Zara Ali";
      Book2.subject =  "Telecom Billing Tutorial";
      Book2.book_id = 6495700;

      /* 打印 Book1 信息 */
      Console.WriteLine( "Book 1 title : {0}", Book1.title);
      Console.WriteLine("Book 1 author : {0}", Book1.author);
      Console.WriteLine("Book 1 subject : {0}", Book1.subject);
      Console.WriteLine("Book 1 book_id :{0}", Book1.book_id);

      /* 打印 Book2 信息 */
      Console.WriteLine("Book 2 title : {0}", Book2.title);
      Console.WriteLine("Book 2 author : {0}", Book2.author);
      Console.WriteLine("Book 2 subject : {0}", Book2.subject);
      Console.WriteLine("Book 2 book_id : {0}", Book2.book_id);       

      Console.ReadKey();

   }
}</code></pre>
  

编译执行上述代码，得到如下结果：
  
<pre><code>Book 1 title : C Programming
Book 1 author : Nuha Ali
Book 1 subject : C Programming Tutorial
Book 1 book_id : 6495407
Book 2 title : Telecom Billing
Book 2 author : Zara Ali
Book 2 subject : Telecom Billing Tutorial
Book 2 book_id : 6495700</code></pre>
  
## 结构体的特征
  
你已经使用了一个名为 Books 的简单结构体。C# 中的结构体与传统的 C 或者 C++ 有明显的不同。 C# 中的结构体有以下特征：

- 结构体可以有方法，域，属性，索引器，操作方法，和事件。
- 结构体可以定义构造函数，但是不能构造析构函数。尽管如此，你还是不能定义一个结构体的默认构造函数。默认构造函数是自动定义的，且不能被改变。
- 与类不同，结构体不能继承其他的结构体或这其他的类。
- 结构体不能用于作为其他结构或者类的基。
- 结构体可以实现一个或多个接口。
- 结构体成员不能被指定为抽象的，虚拟的，或者保护的对象。
- 使用 **New** 运算符创建结构体对象时，将创建该结构体对象，并且调用适当的构造函数。与类不同的是，结构体的实例化可以不使用 New 运算符。
- 如果不使用 New 操作符，那么在初始化所有字段之前，字段将保持未赋值状态，且对象不可用。
  
## 类和结构体
  
类和结构体有以下几个主要的区别：
  
- 类是引用类型，结构体是值类型
- 结构体不支持继承
- 结构体不能有默认构造函数

针对上述讨论，让我们重写前面的例子：
  
<pre><code>using System;
struct Books
{
   private string title;
   private string author;
   private string subject;
   private int book_id;
   public void getValues(string t, string a, string s, int id)
   {
      title = t;
      author = a;
      subject = s;
      book_id = id;
   }
   public void display()
   {
      Console.WriteLine("Title : {0}", title);
      Console.WriteLine("Author : {0}", author);
      Console.WriteLine("Subject : {0}", subject);
      Console.WriteLine("Book_id :{0}", book_id);
   }

};  

public class testStructure
{
   public static void Main(string[] args)
   {

      Books Book1 = new Books();    /* 将 Book1 声明为 Book 类型  */
      Books Book2 = new Books();    /* 将 Book2 声明为 Book 类型 */

      /* book 1 详细信息 */
      Book1.getValues("C Programming",
      "Nuha Ali", "C Programming Tutorial",6495407);

      /* book 2 详细信息 */
      Book2.getValues("Telecom Billing",
      "Zara Ali", "Telecom Billing Tutorial", 6495700);

      /* 打印 Book1 信息 */
      Book1.display();

      /* 打印 Book2 信息 */
      Book2.display(); 

      Console.ReadKey();

   }
}</code></pre>
  
编译执行上述代码，得到如下结果：
 
<pre><code>Title : C Programming
Author : Nuha Ali
Subject : C Programming Tutorial
Book_id : 6495407
Title : Telecom Billing
Author : Zara Ali
Subject : Telecom Billing Tutorial
Book_id : 6495700</code></pre>
  
