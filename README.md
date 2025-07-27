# Todolist_in_python
import json
import os

class ContactManager:
    def __init__(self,filename="contacts.json"):
        self.filename=filename
        self.contacts =load_contacts
  

def load_contacts(self):
    if os.path.exists(self.filename):
        with open(self.filename, "r")as file:
            return json.load(file)
    else:
        return[]
    
def save_contacts(self):
    with open(self.filename, "w")as file:
        json.dump(self.contacts, file, indent=4)

def add_contacts(self,name, phone, email):
    contact = {
        'name': name,
        'phone': phone,
        'email': email 
    }
    self.contacts.append(contact)
    self.save_contacts()
def view_contact(self,name):
    if not view_contact:
        print("NO contacts yet")
    else:
        for c in view_contact:
            print(f"{c[name]} {c["phone"]} {["email"]}")

def search_contact(self,name):
    for contact in self.contacts:
        if contact['name'].lower()==name.lower(): 
            return contact
        return None
def delete_contact(self,name):
    contact=self.search_contact(name)
    if contact:
        self.contact.remove(contact)
        self.save_contacts()
        print(f"contact{name} dedleted successfully.")
    else:
        print(f"Contact{name}not found.")

def update_contact(self,name):
    contact=self.search_contact(name)
    for contact in contact:
        if contact['name'].lower()==name.lower():
            contact["phone"] = input("New Phone")
            contact["email"] = input("New email")
            print("contact deleted ")
            return
        print("contact not found")

 
def main():
    manager = ContactManager()


    while True:
        print("\n---Contect Book Menu---")
        print("1. Add contact")
        print("2. Update contact")
        print("3. Delete contact")
        print("4. Search contect")
        print("5. view")
        print("EXIT")

        choice = input("choose (1-6): ")

        if choice =="1":
            name = input("Enter input : ")
            phone = input("Enter phone number :")
            email = input("Enter email :")
            manager.add_contact(name,phone,email)
        elif choice == "2":
            contact =input("Enter updated contact")
            manager.update_contact(contact)
        elif choice =="3":
            name = input("Enter name to delete :")
            manager.delete_contact(name)
        elif choice=="5":
            manager.view_contact()
        elif choice == "6":
            break 
        else:
            print("please choose a valid option....!!!!")
 

if __name__=="__main__":
    main()
