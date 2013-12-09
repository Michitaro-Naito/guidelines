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

None


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
None


## Source control

### Quality First
Commit qualified changes only.
Avoid commiting partially-implemented changes nor buggy changes.

### Test case
Add test cases when you are implementing a complex functionality like a WebAPI.

### Commit per functionality
Commit changes per functionality.
If you commit multiple functionalities once, you will have trouble when you want to roll one of them back.

### Commit up to several times/day
Most engineers can implement 1-7 functionalities per day.
Avoid unnecessary commits.


## Troubleshooting

### Fix before implement
If there are known bugs, fix them before implementing new one.

### Report and Discuss
Most troubles can be solved unless left.
First of all, tell us if you have any troubles.


## See Also
[Mono Coding Guidelines](http://www.mono-project.com/Coding_Guidelines)
[CakePHP Coding Standards](http://book.cakephp.org/2.0/en/contributing/cakephp-coding-conventions.html)
