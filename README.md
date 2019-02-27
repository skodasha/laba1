# laba1
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace Lab1
{
    class Owner
    {
        public string Name
        {
            get;set;
        }
        public int Age
        {
            get;set;
        }
        public int Capital
        {
            get;set;
        }
        public Boolean CreditStatus
        {
            get;set;
        }

        public Owner(String name, int age, int capital,Boolean creditStatus)
        {
            Name = name;
            Age = age;
            Capital = capital;
            CreditStatus = creditStatus;
        }
    }

    class Technique
    {
        public string Name
        {
            get; set;
        }

        public int Cost
        {
            get; set;
        }
        public int Warranty
        {
            get; set;
        }
        public Owner Owner
        {
            get; set;
        }

        public Technique(String name, int cost, int warranty, Owner owner)
        {
            Name = name;
            Cost = cost;
            Warranty = warranty;
            Owner = owner;
        }

        public void OutputInfo(Technique deviсe)
        {
            Console.WriteLine("name:{0} cost:{1}, warranty:{2}, owner:{3}", deviсe.Name, deviсe.Cost, deviсe.Warranty, deviсe.Owner);
        }
    }

    class Other:Technique
    {
        public string Type
        {
            get;set;
        }
        public Other(String name, int cost, int warranty, Owner owner, int ram, int displaySize, String producer, String cpu, String type) : base(name, cost, warranty, owner)
        {
            Type = type;
        }

    }

    class Computer : Technique
    {

        public int Ram
        {
            get; set;
        }
        public int DisplaySize
        {
            get; set;
        }
            
        public string Producer
        {
            get; set;
        }
        public string Cpu
        {
            get; set;
        }

        public Computer(String name, int cost, int warranty, Owner owner, int ram, int displaySize, String producer, String cpu):base(name, cost, warranty, owner)
        {
            Ram = ram;
            DisplaySize = displaySize;
            Producer = producer;
            Cpu = cpu;
        }
    }

    class Laptop:Computer
    {
        public float Weight
        {
            get; set;
        }
        public int BatteryLife
        {
            get; set;
        }

        public Laptop(String name, int cost, int warranty, Owner owner, int ram, int displaySize, String producer, String cpu, float weight, int batteryLife)
            :base(name, cost, warranty, owner, ram, displaySize, producer, cpu)
        {
            Weight = weight;
            BatteryLife = batteryLife;
        }
    }

    class Personal:Computer
    {
        public Boolean Keyboard
        {
            get; set;
        }
        public Boolean Mouse
        {
            get;set;
        }
        public Personal(String name, int cost, int warranty, Owner owner, int ram, int displaySize, String producer, String cpu, 
            float weight, int batteryLife, Boolean keyboard, Boolean mouse)
            : base(name, cost, warranty, owner, ram, displaySize, producer, cpu)
        {
            Keyboard = keyboard;
            Mouse = mouse;
        }
    }
    class Program
    {
        static void Main(string[] args)
        {
            Computer computer = new Computer("Computer",450, 3, new Owner("Vova",25,1000,false),16,16,"Asus","core i7");
            computer.OutputInfo(computer);

            Laptop laptop = new Laptop("Laptop", 1500, 2, new Owner("Masha",27,3000,true),8,13,"Acer","core i7", 1, 15);
            laptop.OutputInfo(laptop);

            Console.ReadLine();
        }
    }
}
