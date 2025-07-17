# task4
Напишите метод, который будет вычислять угол между часовой и минутной стрелками часов. На вход функции подаётся время в виде двух переменных: "hours" и "minutes".
Расчет угла производить относительно реального поведения стрелок часов.

```csharp filename="Program.cs"
using System.ComponentModel;

    static double CalvulateAngle(int hours, int minutes)
    {
        hours = hours % 12;

        double h_Angle = (hours * 30) + (minutes * 0.5);
        double min_Angle = minutes * 6;

        double angel = Math.Abs(h_Angle - min_Angle);

        return (angel);
    }


int hours = -1;
int minutes = -1;
Boolean f;
Console.WriteLine("Input hour in format '0,1,2...24'");

while (true )
{
    try
    {
        hours = Convert.ToInt16(Console.ReadLine());
    }
    catch (Exception e)
    {
        Console.WriteLine("Sorry, your input is invalid, try again");
    }

    if ((hours >= 0) && (hours <= 24))
    {
        break;
    }
}

Console.WriteLine("Input minute in format '0,1,2...60'");
while (true)
{
    try
    {
        minutes = Convert.ToInt16(Console.ReadLine());
    }
    catch (Exception e)
    {
        Console.WriteLine("Sorry, your input is invalid, try again");
    }

    if ((minutes >= 0) && (minutes < 60))
    {
        break;
    }
}

string s_h = Convert.ToString(hours);
string s_m = Convert.ToString(minutes);

if (hours < 10)
{
    s_h = '0' + Convert.ToString(hours);
}
if (minutes < 10)
{
    s_m = '0' + Convert.ToString(minutes);
}

Console.WriteLine($"Your choose clock arms position {s_h}:{s_m}");

Console.WriteLine($"The Angle is {CalvulateAngle(hours, minutes)} degrees");
```