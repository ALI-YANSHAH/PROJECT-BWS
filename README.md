# PROJECT-BWS
data programming project

class RetailManagement:
    def __init__(self):
        self.items = {}

    def display_items(self):
        print("Displaying Items:")
        for item_id, item_name in self.items.items():
            print(f"{item_id}: {item_name}")

    def search_item(self):
        item_id = input("Enter Item ID to search: ")
        if item_id in self.items:
            print(f"Item found: {self.items[item_id]}")
        else:
            print("Item not found.")

    def add_item(self):
        item_name = input("Enter Item Name: ")
        item_id = str(len(self.items) + 1)
        self.items[item_id] = item_name
        print(f"Item '{item_name}' added with ID {item_id}.")

    def edit_item(self):
        item_id = input("Enter Item ID to edit: ")
        if item_id in self.items:
            new_item_name = input(f"Enter new name for {self.items[item_id]}: ")
            self.items[item_id] = new_item_name
            print("Item edited successfully.")
        else:
            print("Item not found.")

    def delete_item(self):
        item_id = input("Enter Item ID to delete: ")
        if item_id in self.items:
            deleted_item_name = self.items.pop(item_id)
            print(f"Item '{deleted_item_name}' deleted.")
        else:
            print("Item not found.")

    def delete_all_items(self):
        self.items = {}
        print("All items deleted.")

    def add_to_purchase(self):
        # Add your purchase logic here
        print("Adding to purchase...")

    def main_menu(self):
        while True:
            print("\nRetail Management Application Menu:")
            print("1. Display Items\n2. Search Item\n3. Add Item\n4. Edit Item\n5. Delete Item")
            print("6. Delete All Items\n7. Add to Purchase\n9. Exit")

            choice = input("Enter your choice (1-9): ")

            if choice == '1':
                self.display_items()
            elif choice == '2':
                self.search_item()
            elif choice == '3':
                self.add_item()
            elif choice == '4':
                self.edit_item()
            elif choice == '5':
                self.delete_item()
            elif choice == '6':
                self.delete_all_items()
            elif choice == '7':
                self.add_to_purchase()
            elif choice == '9':
                print("Exiting the Retail Management Application. Goodbye!")
                break
            else:
                
                print("Invalid choice. Please enter a number between 1 and 9.")

if __name__ == "__main__":
    username = input("Enter your username: ")
    print(f"Welcome {username}. Happy Working!!")

    retail_management = RetailManagement()
    retail_management.main_menu()
