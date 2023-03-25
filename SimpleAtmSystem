using System;
using System.Collections.Generic;
using System.Net.Http.Headers;
using System.Runtime;
namespace SimpleAtmSystem
{
    public class CardHolder
    {
         string FirstName;
         string LastName;
         string CardNum;
         int PIN;
         double Balance;
        public CardHolder(){ }
        public CardHolder(string FirstName, string LastName, string CardNum, int PIN, double Balance)
        {
            this.FirstName = FirstName;
            this.LastName = LastName;
            this.CardNum = CardNum;
            this.PIN = PIN;
            this.Balance = Balance;
        }
        public void SetFirstName(string FirstName)
        {
            this.FirstName = FirstName;
        }
        public void SetLastName(string LastNam)
        {
            LastName = LastNam;
        }
        public void SetCardNum(string CardNum)
        {
            this.CardNum = CardNum;
        }
        public void SetPIN(int PIN)
        {
            this.PIN = PIN;
        }
        public void SetBalance(double Balance)
        {
            this.Balance = Balance;
        }
        public string GetFirstName()
        {
            return FirstName;
        }
        public string GetLastName()
        {
            return LastName;
        }
        public string GetCardNum()
        {
            return CardNum;
        }
        public int GetPIN()
        {
            return PIN;
        }
        public double GetBalance()
        {
            return Balance;
        }
    }
    public class Program
    {
  
        static void Main(string[] args)
        {
            void printOptions()
            {
                Console.WriteLine("leas choose one of the followin options...");
                Console.WriteLine("1: Deposit");
                Console.WriteLine("2: withdraw");
                Console.WriteLine("3: Show balance");
                Console.WriteLine("4: Exit");
                Console.WriteLine("********************************************");
            }
            void desposit(CardHolder currentUser)
            {
                Console.WriteLine("How much woud you like to desposet? ");
                double desposetNum = double.Parse(Console.ReadLine());
                currentUser.SetBalance(desposetNum+currentUser.GetBalance());
                Console.WriteLine("Thank you for your deposit, your new balance is: "+currentUser.GetBalance());
            }
            void withdraw(CardHolder currentUser)
            {
                Console.WriteLine("How much woud you like to withdraw? ");
                double withdrawNum = double.Parse(Console.ReadLine());
                if (withdrawNum > currentUser.GetBalance())
                {
                    Console.WriteLine("The balance is insufficient");
                }
                else
                {
                    Console.WriteLine("Please withdraw the card and wait for the money");
                    currentUser.SetBalance(currentUser.GetBalance() - withdrawNum);
                }

            }
            void balance(CardHolder currentUser)
            {
                Console.WriteLine("current balance is: "+ currentUser.GetBalance());
            }
            List<CardHolder> users = new List<CardHolder>();
            users.Add(new CardHolder("mohmed", "shawky", "268391788362349", 132000, 1000000));
            users.Add(new CardHolder("shawky", "helmy", "163591789962332", 131991, 1000));
            users.Add(new CardHolder("helmy", "zeedn", "368091086342225", 131881, 0));
            Console.WriteLine("Welcom to our ATM");
            Console.WriteLine("Pleas insert your number of card:");
            string userCardNum = "";
            CardHolder currentUser = new CardHolder();
            while (true)
            {
                try
                {
                    userCardNum = Console.ReadLine();
                    currentUser = users.FirstOrDefault(x => x.GetCardNum() == userCardNum);//search in list
                    if (currentUser != null) break;
                    else Console.WriteLine("Card not recognized,please try again");
                }
                catch { Console.WriteLine("Card not recognized,please try again"); }
            }
            Console.WriteLine("pleas enter your PIN: ");
            int pinNum = 0;
            while (true)
            {
                try
                {
                    pinNum =int.Parse(Console.ReadLine());
                    if (currentUser.GetPIN()==pinNum) break;
                    else Console.WriteLine("Icorrect PIN,please try again");
                }
                catch { Console.WriteLine("Icorrect PIN,please try again"); }
            }
            Console.WriteLine("Welcom "+currentUser.GetFirstName()+" "+currentUser.GetLastName());
            int option = 0;
            bool ok = true;
            do
            {
                if(ok)Console.Write('P');
                printOptions();
                option = int.Parse(Console.ReadLine());
                if (option < 1 || option > 4)
                {
                    Console.Write("Recognize number p");
                    ok = false;
                }
                if (option == 1)
                {
                    desposit(currentUser);
                    ok = true;
                }
                else if (option == 2)
                {
                    withdraw(currentUser);
                    ok = true;
                }
                else if (option == 3)
                {
                    balance(currentUser);
                    ok = true;
                }
                } while (option != 4);
            Console.WriteLine("Thank you have a nice day");
        }
    }
}
