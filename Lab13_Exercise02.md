# Lab 13 Exercise 2

## call from interface references

1.สร้าง console application project

```cmd
dotnet new console --name Lab13_Ex02
```

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
IMovable [] animals = new Animal[3];
animals[0] = new Dog();
animals[1] = new Dog();
animals[2] = new Dog();

foreach (var animal in animals)
{
    animal.Move();
}

interface IMovable
{
    public void Move();
}

abstract class Animal : IMovable
{
    abstract public void Move();
}
class Dog : Animal
{
    public override void Move()
    {
        System.Console.WriteLine("Dog move by running on the ground");
    }
}

```

3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab13_Ex02
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3
<img width="792" alt="Screenshot 2024-03-29 190621" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-13/assets/144196049/da8577f4-d59a-4f40-aa19-a314b2942106">

#### สามารถ Build ได้ เพราะ Dog เป็นคลาสที่สืบทอดมาจาก Animal ซึ่งเป็น abstract class และ Animal ได้ implement interface IMovable ด้วยเมทอด Move() ดังนั้น Dog จึงต้อง Override เมทอด Move()
5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab13_Ex02
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
<img width="792" alt="Screenshot 2024-03-29 190648" src="https://github.com/SuphawadiP/03376836-OOP-2566-Lab-13/assets/144196049/faa12b14-ed9c-48fa-8b3d-8bf14461972b">

#### สามา Run ได้ เพราะ ใช้ Move() จาก object ในอาร์เรย์ IMovable ได้โดยตรง โดยไม่จำเป็นต้องรู้ว่า object นั้นเป็นคลาสชนิดใด ด้วยคุณสมบัติของ Polymorphism ที่เป็นลักษณะของการใช้ Interface
7.อธิบายสิ่งที่พบในการทดลอง
#### Dog move by running on the ground
#### Dog move by running on the ground
#### Dog move by running on the ground
