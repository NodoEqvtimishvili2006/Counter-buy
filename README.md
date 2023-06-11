using System;

public class Weapon
{
    public string Name { get; set; }
    public int Price { get; set; }

    public Weapon(string name, int price)
    {
        Name = name;
        Price = price;
    }
}

public class Player
{
    public string Name { get; set; }
    public int Money { get; set; }

    public Player(string name, int money)
    {
        Name = name;
        Money = money;
    }

    public void BuyWeapon(Weapon weapon)
    {
        if (Money >= weapon.Price)
        {
            Money -= weapon.Price;
            Console.WriteLine($"Congratulations! {Name} bought the {weapon.Name}.");
        }
        else
        {
            Console.WriteLine($"Sorry, {Name} does not have enough money to buy the {weapon.Name}.");
        }
    }
}

public class Program
{
    public static void Main(string[] args)
    {
       
        Weapon rifle = new Weapon("Rifle", 500);
        Weapon pistol = new Weapon("Pistol", 300);
        Player player = new Player("John", 1000);
        player.BuyWeapon(rifle);
        player.BuyWeapon(pistol);
    }
}
