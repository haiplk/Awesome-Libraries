## Introduction
SOLID is an acronym that represents five principles of object-oriented design and programming. These principles were introduced by Robert C. Martin (commonly known as Uncle Bob) and are aimed at making software designs more understandable, flexible, and maintainable
## Key Principles

### 1. Single Responsibility Principle (SRP)
Principle: A class should have only one reason to change. In other words, a class should have only one responsibility or job.

### 2. Open/Closed Principle (OCP)
Principle: Software entities (classes, modules, functions, etc.) should be open for extension but closed for modification.

```csharp
// Bad
public class DiscountCalculator
{
    public double CalculateDiscount(double price, string discountType)
    {
        if (discountType == "Percentage")
            return price * 0.1;
        else if (discountType == "Fixed")
            return price - 10;
        // More conditions...
    }
}

// Good
public interface IDiscountCalculator
{
    double CalculateDiscount(double price);
}

public class PercentageDiscountCalculator : IDiscountCalculator
{
    public double CalculateDiscount(double price)
    {
        return price * 0.1;
    }
}
```

### 3. Liskov Substitution Principle (LSP)
Principle: Objects of a superclass should be replaceable with objects of its subclasses without affecting the correctness of the program.


```csharp
// Violate 
```
// Superclass
public class Shape
{
    public virtual double Area()
    {
        return 0;
    }
}

// Subclass
public class Rectangle : Shape
{
    public double Width { get; set; }
    public double Height { get; set; }

    public override double Area()
    {
        return Width * Height;
    }
}

// Another subclass
public class Square : Shape
{
    public double SideLength { get; set; }

    public override double Area()
    {
        return SideLength * SideLength;
    }
}

class Program
{
    static void Main(string[] args)
    {
        // Using polymorphism
        Shape shape1 = new Rectangle { Width = 5, Height = 4 };
        Shape shape2 = new Square { SideLength = 5 };

        // Violating Liskov Substitution Principle
        shape2 = new Rectangle { Width = 5, Height = 4 }; // A square is not a rectangle!

        // Calculating and printing areas
        Console.WriteLine("Area of shape1 (Rectangle): " + shape1.Area());
        Console.WriteLine("Area of shape2 (Square): " + shape2.Area());
    }
}
```csharp

// Good
public abstract class Shape
{
    public abstract int Area();
}

public class Rectangle : Shape
{
    public int Width { get; set; }
    public int Height { get; set; }

    public override int Area() => Width * Height;
}

public class Square : Shape
{
    public int Side { get; set; }

    public override int Area() => Side * Side;
}
```
