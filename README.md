```csharp
using System;
using System.Collections.Generic;
using System.Linq;

public class Student
{
    public int ID { get; set; }
    public string Name { get; set; }
    public int Age { get; set; }
    public override string ToString()
    {
        return $"ID: {ID}, Name: {Name}, Age: {Age}";
    }
}

public class Program
{
    public static void Main()
    {
        // List Danh sach hoc sinh
        List<Student> students = new List<Student>()
        {
            new Student { ID = 1, Name = "Nghia", Age = 18 },
            new Student { ID = 2, Name = "Teo", Age = 15 },
            new Student { ID = 3, Name = "Nam", Age = 19 },
            new Student { ID = 4, Name = "An", Age = 23 },
            new Student { ID = 5, Name = "Nia", Age = 20 }
        };

        // a
        Console.WriteLine("Danh sach toan bo hoc sinh:");
        foreach (var student in students)
        {
            Console.WriteLine(student);
        }

        // b
        var age15_18 = students.Where(s => s.Age >= 15 && s.Age <= 18);
        Console.WriteLine("\nHS tu 15 den 18:");
        foreach (var student in age15_18)
        {
            Console.WriteLine(student);
        }

        // c
        var nameStartsWithA = students.Where(s => s.Name.StartsWith("A"));
        Console.WriteLine("\nHS co ten bat dau bang chu 'A':");
        foreach (var student in nameStartsWithA)
        {
            Console.WriteLine(student);
        }
        // d
        var Tong = students.Sum(s => s.Age);
        Console.WriteLine("\nTong tuoi cua tat ca HS la: " + Tong);
        // e.   
        var oldest = students.OrderByDescending(s => s.Age).FirstOrDefault();
        Console.WriteLine("\nHS co tuoi lon nhat la:" + oldest);
        // f
        var sortedStudents = students.OrderBy(s => s.Age);
        Console.WriteLine("\nDanh sach HS co tuoi tang dan:");
        foreach (var student in sortedStudents)
        {
            Console.WriteLine(student);
        }
    }
}
