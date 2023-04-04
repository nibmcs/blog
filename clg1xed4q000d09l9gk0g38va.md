---
title: "LINQ in C#"
seoTitle: "Exploring LINQ in C#: Syntax and Examples"
seoDescription: "Learn about LINQ in C#, a powerful feature that simplifies querying data from different sources with syntax examples and code. Boost your C# skills!"
datePublished: Tue Apr 04 2023 07:15:27 GMT+0000 (Coordinated Universal Time)
cuid: clg1xed4q000d09l9gk0g38va
slug: linq-in-csharp
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/W-LQbAUhE64/upload/73ce8b2d23569067c3be66bfabf8f197.jpeg
tags: csharp, net-core, linq, net-framework, datastructure

---

### Introduction

LINQ (Language Integrated Query) is a powerful feature of C# that provides a simple and concise syntax to query data from various data sources, including objects, databases, XML files, and others. It was developed by a team of engineers at Microsoft, including Anders Hejlsberg, Matt Warren, Erik Meijer, and Bart De Smet. LINQ was first introduced as a part of the .NET Framework 3.5 release in 2007 and has become an integral part of the C# programming language. It offers a consistent model for working with data across various types of data sources and formats, simplifying the process of querying and transforming data. With LINQ, developers can use the same basic coding patterns to query and manipulate data in different formats, including XML documents, SQL databases, ADO.NET Datasets, and .NET collections, among others. In this blog, I will explore LINQ in C# with code examples.

### **LINQ Syntax**

**LINQ syntax consists of three main parts,**

1. Data Source: It is the collection of data from which we want to query data.
    
2. Query: It is the expression that we want to perform on the data source.
    
3. Result: It is the output of the query expression.
    

**LINQ supports both method syntax and query syntax.**

1. Method Syntax: In method syntax, we use extension methods to perform operations on the data source. The method syntax is more concise and faster than query syntax.
    
2. Query Syntax: In query syntax, we use a SQL-like syntax to query data from the data source. Query syntax is more readable and easy to understand.
    

Here are two examples that demonstrate the same approach using both Method Syntax and Query Syntax

Method Syntax :

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

// Method Syntax
var evenNumbers = numbers.Where(n => n % 2 == 0);

foreach (var number in evenNumbers)
{
    Console.WriteLine(number);
}
```

Query Syntax:

```csharp
var numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

// Query Syntax
var evenNumbers =
    from number in numbers
    where number % 2 == 0
    select number;

foreach (var number in evenNumbers)
{
    Console.WriteLine(number);
}
```

In both examples, I have a list of integers and we are using LINQ to select only the even numbers. In the Method Syntax example, we are using the `Where` extension method to perform the operation, and in the Query Syntax example, we are using a SQL-like syntax to query the data. Both examples will produce the same output.

### **LINQ Examples**

**Querying a List:**

We can query a List using LINQ in C#. Here is an example:

```csharp
List<int> numbers = new List<int> { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
var evenNumbers = from number in numbers
                  where number % 2 == 0
                  select number;
foreach (var number in evenNumbers)
{
    Console.WriteLine(number);
}
```

*Output is,*

`2`

`4`

`6`

`8`

`10`

In this example, we have a List of integers from 1 to 10. We use query syntax to query even numbers from the List using the 'where' clause. The 'select' clause is used to select even numbers from the List. Finally, we iterate through the even numbers using a foreach loop and display them.

**Querying an Array:**

We can query an array using LINQ in C#. Here is an example:

```csharp
int[] numbers = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };
var evenNumbers = numbers.Where(n => n % 2 == 0);
foreach (var number in evenNumbers)
{
    Console.WriteLine(number);
}
```

*Output is,*

`2`

`4`

`6`

`8`

`10`

In this example, we have an array of integers from 1 to 10. We use method syntax to query even numbers from the array using the 'Where' extension method. Finally, we iterate through the even numbers using a foreach loop and display them.

**Querying a Collection of Objects:**

We can query a collection of objects using LINQ in C#. Here is an example:

```csharp
class Employee
{
    public int Id { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
}
List<Employee> employees = new List<Employee>
{
    new Employee { Id = 1, Name = "John", Age = 30 },
    new Employee { Id = 2, Name = "Mary", Age = 25 },
    new Employee { Id = 3, Name = "Mark", Age = 35 },
    new Employee { Id = 4, Name = "Sara", Age = 28 },
    new Employee { Id = 5, Name = "Peter", Age = 40 }
};
var result = from employee in employees
             where employee.Age > 30
             select employee;
foreach (var employee in result)
{

    Console.WriteLine("Id: {0}, Name: {1}, Age:{2}",
                              employee.Id,employee.Name, employee.Age);
}
```

*Output is,*

`Id: 3, Name: Mark, Age: 35`

`Id: 5, Name: Peter, Age: 40`

In this example, we have a collection of Employee objects. We use query syntax to query employees who are above 30 years of age using the 'where' clause. The 'select' clause is used to select employees who are above 30 years of age. Finally, we iterate through the result using a foreach loop and display their Id, Name, and Age.

**Querying a Database:**

We can query a database using LINQ in C#. Here is an example:

```csharp
using (var db = new DataContext())
{
    var result = from customer in db.Customers
    where customer.City == "London"
    select customer;
    foreach (var customer in result)
    {
        Console.WriteLine("Name: {0}, City: {1}", customer.Name,
            customer.City);
    }
}
```

In this example, we use LINQ to query a database using the 'DataContext' class. We query customers who live in London using the 'where' clause. Finally, we iterate through the result using a foreach loop and display their Name and City.

### **Conclusion**

In conclusion, LINQ (Language Integrated Query) is a powerful feature in C# that offers a simple and concise syntax for querying and manipulating data from various sources. LINQ has become an integral part of the C# programming language and provides a consistent model for working with data across various types of data sources and formats. The blog explored LINQ syntax, including method syntax and query syntax, and provided several examples of querying data from different sources, such as lists, arrays, collections of objects, and databases. Developers can use LINQ to write code that is both readable and easy to understand, and also faster and more efficient. Overall, LINQ is a valuable tool for developers to work with data in C# and helps to simplify the process of querying and transforming data.