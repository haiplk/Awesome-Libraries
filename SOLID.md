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
// Bad
public class Rectangle
{
    public virtual int Width { get; set; }
    public virtual int Height { get; set; }
}

public class Square : Rectangle
{
    public override int Width
    {
        get => base.Width;
        set
        {
            base.Width = value;
            base.Height = value;
        }
    }

    public override int Height
    {
        get => base.Height;
        set
        {
            base.Width = value;
            base.Height = value;
        }
    }
}

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
