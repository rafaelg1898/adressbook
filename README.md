using System;
using System.Collections;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace adressbook
{
    class Program
    {
        private static Addressbook addressbook = new Addressbook();
        
        static void Main(string[] args)
        {
            Contact rafael = new Contact();
            rafael.Id = 1;
            rafael.Name = "Rafael";
            rafael.Phone = "809-591-0409";
            rafael.Email = "rafaelg1898@gmail.com";
            
            Contact rafael2 = new Contact();
            rafael2.Id = 2;
            rafael2.Name = "Rafael Arturo";
            rafael2.Phone = "809-591-0408";
            rafael2.Email = "rafaelarturo@gmail.com";

            addressbook.addContact(rafael);
            addressbook.addContact(rafael2);

             Console.WriteLine("All contacts");
             printList(addressbook.getList());

               string search = "Rafael";
                Console.WriteLine("Search: " + search);
                printList(addressbook.getList(search));

            int delete;
            int = Convert.ToInt32(Console.ReadLine());




            Console.ReadKey();
            
        }

        public static void printList(ArrayList list)
        {
            foreach (Contact contact in list)
            {
                contact.print();

                
            }
        }

    }

    public class Contact
    {
        int id;
        string name, email, phone;
        
        public string Name { get => name; set => name = value; }
        public string Email { get => email; set => email = value; }
        public string Phone { get => phone; set => phone = value; }
        public int Id { get => id; set => id = value; }
       
        public void print()
        {
            Console.WriteLine(Id + "\n" + Name + "\n" + Phone + "\n" + Email);
        }



        
    }

    public class Addressbook
    {
        ArrayList contacts = new ArrayList();

        public void addContact (Contact contact)
        {
            contacts.Add(contact);
        }

       

        public ArrayList getList ()
        {
            return contacts; 
        }

        public ArrayList getList(string search)
        {
            ArrayList list = new ArrayList();
            foreach (Contact contact in contacts)
            {
                if (contact.Name == search)
                {
                            list.Add(contact);
                        }
                    }
                    return list;
        } 


              
        
        


    }
    
}
