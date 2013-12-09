# Guidelines


## Common

### Priority of Guidelines
1. Project Requirements
2. This Document
3. Framework
4. Programming Language

### Unless required

### Languages
Use English.

### Encoding
Use UTF-8.

### Legal
Never violate any kind of Intellectual Property Rights (copyrights, patents, trademarks etc.).


## Basic Principles

### Rules of least surprise

### Keep it short and simple (KISS)

### You ain't gonna need it (YAGNI)

### Don't repeat yourself (DRY)

### Use pseudo codes than flow-charts

### Be Stable and Maintainable
It is more important to be stable than to be fast.
It is more important to be maintainable than to be fast.

### Name and Case like C-Sharp
good:
```csharp
// C#
public class Bakery{
  string _shopName = "bar";
  public List<Customer> customers = new List<Customer>(){
    new Customer("Alice"),
    new Customer("Bob")
  };
  
  public void Bake(int amount){
    // ...
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
  
  public function Bake($amount){
    // ...
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
  
  s.Bake = function(amount){
    // ...
  }
}
```

```css
/* CSS */
.foo{
  text-align: center;
}
```

```html
<!-- HTML -->
<p>foo</p>
```

bad:
```php
public function getItems(){
}
```
```php
public function get_items(){
}
```

### Comment anything
codes and tables

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


## Database

### Singular
Use singular names for fields.


## Web Programming - Server

### Languages
Use C#, PHP


## Web Programming - Client
JavaScript, jQuery, knockout.js


## Native Programming
C#


## Source control

### No garbage

### Per functionality

### Up to 2 times/day


Fix 

Report

Discuss

Quality

C#: Mono Coding Guidelines
CakePHP: CakePHP Coding Standards
