# Guidelines



## Common

### Purposes
These guidelines are written to encourage you to keep your codes, databases and projects clean.
**Short, Simple, Stable and Maintainable** codes will help us in the future.
Please follow these instructions if you are willing to cooperate with us. ;)

### Priority of Guidelines
1. Project Requirements
2. This Document
3. Framework
4. Programming Language

### Languages
Most up-to-date documents are written ONLY in English.
Please use English and forget about your mother tongue for a while.

### Encoding
UTF-8

### Legal
Never violate any kind of Intellectual Property Rights (e.g. copyrights, patents, trademarks.).
In the most cases, lawsuits will cost us x100 than what we earn. :(



## Basic Principles

### Principle of least surprise
[Principle of least surprise](http://en.wikipedia.org/wiki/Principle_of_least_astonishment)

### Keep it short and simple (KISS)
[KISS Principle](http://en.wikipedia.org/wiki/KISS_principle)

### You ain't gonna need it (YAGNI)
[YAGNI Principle](http://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

### Don't repeat yourself (DRY)
[DRY Principle](http://en.wikipedia.org/wiki/Don%27t_repeat_yourself)

good:
```sql
select name from customer;
```

```csharp
var customer = new Customer("Alice");
customer.DoSomething();
```

bad:
```sql
select customer_name from customer;
```

```csharp
Customer customer = new Customer("Alice");
customer.DoSomething();
```

### Be Stable and Maintainable
It is more important to be stable and maintainable than to be fast-coding.


### Prefer Pseudo Codes than Flowcharts
In the most cases, drawing Flowcharts takes your time.
Use Pseudo Codes to explain your logic.

good:
```csharp
foreach(var c in customers){
  if(c.IsOldFormat)
    c.UpgradeFormat();
}
```

bad:

An equivalent flowchart.


### Name and Case like C-Sharp
[.NET Framework Class Library](http://msdn.microsoft.com/en-us/library/gg145045.aspx)

Sometimes your cooperators are confused by naming and casing.
Standardize them to avoid these situations.
Follow C-Sharp and .NET architectures. (e.g. Pascal casing for method names. Dispose() to clean up an object.)

good:
```csharp
// C#
public class Bakery{
  string _shopName = "bar";
  public List<Customer> customers = new List<Customer>(){
    new Customer("Alice"),
    new Customer("Bob")
  };
  
  public void Dispose(){
    // Dispose this object...
  }
}
```

```php
// PHP
class Bakery{
  private $_shopName = 'Foo Bakery';
  public $customers = array(
    new Customer('Alice'),
    new Customer('Bob')
  );
  
  public function Dispose(){
    // Dispose this object...
  }
}
```

```javascript
// JavaScript
function Bakery(){
  var s = this;
  s._shopName = 'Foo Bakery';
  s.customers = [
    new Customer('Alice'),
    new Customer('Bob')
  ];
  
  s.Dispose = function(amount){
    // Dispose this object...
  }
}
```

bad:

```php
// PHP
class Bakery{
  private $shop_name = 'Foo Bakery';
  public $customers = array(
    new Customer('Alice'),
    new Customer('Bob')
  );
  
  public function free(){
    // Dispose this object...
  }
}
```

### Use useful names
Avoid ambiguous names like "value1, 2, 3" and use obvious names to improve the readability of your code.

good:
```csharp
public class Bakery{
  public Customer[] customers;
  public Customer[] customersPrime;
}
```

bad:
```csharp
public class Bakery{
  public Customer[] customers;
  public Customer[] customers2;
}
```

### Avoid Omission
good:
```csharp
public Customer[] GetCustomers(){
  return _customers;
}
```

bad:
```csharp
public Customer[] GC(){
  return _customers;
}
```

### Comment anything
Comment tables, fields, classes, properties, methods etc. to help your cooperators to understand your tables and codes.

good:
```sql
create table product(
  id int,
  price double comment('Price in USD')
);
```

```csharp
/// <summary>
/// Upgrades data format v1 to v2.
/// </summary>
/// <param name="deleteIfFailed">If true, deletes entire data when failed to upgrade.</param>
public void UpgradeDataFormat(bool deleteIfFailed){
  // ...
}
```

bad:
```sql
create table product(
  id int,
  price double
);
```

```csharp
public void UpgradeDataFormat(bool deleteIfFailed){
  // ...
}
```

### Throw NotImplementedException if not implemented
If you have partially-implemented codes, throw NotImplementedException to let your cooperators know that it's not ready to be called. If neglected, your cooperators may misunderstand that your function is done, try to call it, face misterious errors and waste their time.:(

good:
```csharp
public double CalculateSomething(int a, int b){
  double result = 0;
  // ... Complex, partially implemented calculations here ...
  throw new NotImplementedException();
}
```
bad:
```csharp
public double CalculateSomething(int a, int b){
  double result = 0;
  // ... Complex, partially implemented calculations here ...
  return result;
}
```

### Short Names for Iteration
Use short names for iteration to type less.

good:
```csharp
foreach(var c in customers){
  c.UpdateFoo();
  c.UpdateBar();
  c.DoSomething();
}
```
bad:
```csharp
foreach(var customer in customers){
  customer.UpdateFoo();
  customer.UpdateBar();
  customer.DoSomething();
}
```

### Eliminate Typo Bugs
Humans can typo. Even the greatest programmer types wrong sometimes.
So, we must prevent bugs being produced when we typo.
To do this, pick clearly different names for symbols.

good:
```csharp
var foo = new Foo();
var bar = new Bar();
foo.DoSomething();
bar.DoSomething();  // If you typo here, the program can't be compiled and you can corret it easily.
```
bad:
```csharp
var a = new Foo();
var o = new Bar();
a.DoSomething();
o.DoSomething();  // If you typo "o" to "a", the program can be compiled and run but never work correctly. In addition, you will lose a lot of time to find and fix it...
```

Also, use programming languages which check symbols strictly to avoid this. (If available.)

good:
```csharp
// C#
class Foo{
  public int bar;
}
var foo = new Foo();
foo.bae = 123;  // Typo. Compile error occurs and you can correct it immediately.
```
not good:
```php
// PHP
class Foo{
  public $bar;
}
$foo = new Foo();
$foo->bae = 123;  // Typo. Declears new member variable "bae" happenedly and compile error never occur. This will be a hidden bug...
```


## Database

### Singular
Use singular names for tables not to be confused by irregular, plural nouns. (e.g. fish, automata.)

good:
```sql
create table customer(...);
```

bad:
```sql
create table customers(...);
```


## Web Programming - Server

### Singular
Use singular names for Controllers not to be confused by irregular, plural nouns. (e.g. fish, automata.)

good:
```php
class FooController extends AppController{
  ...
}
```

bad:
```php
class FoosController extends AppController{
  ...
}
```

### Keep Controller simple
Don't make a query at Controller.

good:
```php
class FooController extends AppController{
  public $components = array('Data');
	
  public function Index(){
    $this->set('foos', $this->Data->GetFoos());
  }
}
```

bad:
```php
class FooController extends AppController{
  public function Index(){
    $foos = $this->Foo->find('all', array(
      'conditions'=>array(
        ...
      ),
      'order'=>array(
        ...
      ),
      'limit'=>20,
      ...
    );
    $this->set('foos', $foos);
  }
}
```

### Format, HTML Escape at View
good:
```php
class FooController extends AppController{
  ...
  public function AveragePrice(){
    $price = $this->Data->GetAveragePrice();
    $this->set('price', round($price));
  }
}

// at View
Price: <?php echo round($price); ?>
Text: <?php echo h($text); ?>
```

bad:
```php
class FooController extends AppController{
  ...
  public function AveragePrice(){
    $price = $this->Data->GetAveragePrice();
    $text = "Some user text";
    $this->set('price', round($price));
    $this->set('text', h($text));
  }
}

// at View
Price: <?php echo $price; ?>
Text: <?php echo $text; ?>
```

## Web Programming - Client

### Prefer jQuery than JavaScript
[jQuery](http://jquery.com/)

jQuery is smarter and more reliable than JavaScript.
Use jQuery as long as you can.

good:
```javascript
$('#foo').text('bar');
```

bad:
```javascript
document.getElementById('foo').setText('bar');
```

### Prefer knockout.js than angular.js or backbone.js
[knockout.js](http://knockoutjs.com/)

knockout.js is a balanced and ordered framework to bind data.


## Native Programming

### Use Xamarin for Native Apps
Use Xamarin and C# to make native applications.

good:
```
Write your codes in C# and deploy to Android, iOS and Windows Phone once.
```

bad:
```
Write your codes in Java for Android.
Write your codes in Objective-C for iOS.
Write your codes in C# for Windows Phone.

... Now, you are tired from them. :(
```

### Use Unity3D for Games
Use Unity3D to develop games.
We can deploy the same game for Windows, Mac, Linux, Android, iOS, Windows Phone etc. by ease.


## Source control and issue sharing

### Use GitHub
GitHub provides nice, integrated source control and issue sharing. Use GitHub as long as you can.

### Quality First
Commit qualified changes only.
Avoid commiting partially-implemented changes nor buggy changes.

### Make Story and make it true
When you plan and implement something, make Story (what should be done by user) first and note what are needed to make Story true. Story let your collaborators to understand what kind of functionality will be implemented immediately.

good:
```
Story:
User can sign up.

Needed:
- Registration Form with Email, UserName, Password inputs
- Email Authentication
```

bad:
```
Add Registration Form with Email, UserName, Password inputs and Email Authentication.
```

### Test case
Add test cases when you are implementing a complex functionality like a WebAPI.

### Commit per functionality
Commit changes per functionality.
If you commit multiple functionalities once, you will have trouble when you want to roll one of them back.

### Commit up to several times/day
Most engineers can implement 1-7 functionalities per day.
Avoid unnecessary commits.

### Send pull request which can be merged automatically
Pull request which must be merged manually have highly chance of being rejected because it takes a lot of time of your collaborator. To avoid this, send pull request which can be merged automatically as long as you can.

### Keep branches as short as you can
In the most cases, keeping branches long requires massive efforts.
When you make a branch, make, improve, pull request and delete(when merged successfully) quickly to save your time.


## Troubleshooting

### Fix before implement
If there are known bugs, fix them before implementing new one.

### Report and Discuss
Most troubles can be solved unless left.
First of all, tell us if you have any troubles.
(e.g. Server down, Data loss, Delay of Development, Design mistake, Legal issues, Lack of Skills.)



## See Also
[Mono Coding Guidelines](http://www.mono-project.com/Coding_Guidelines)

[CakePHP Coding Standards](http://book.cakephp.org/2.0/en/contributing/cakephp-coding-conventions.html)
