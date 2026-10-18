
#include <iostream>
#include <vector>
#include <string>
using namespace std;

int main() {
    vector<string> shoppingList;
    int choice;
    string item;

    do {
        cout << "\n--- Shopping List Menu ---\n";
        cout << "1. Add Item\n";
        cout << "2. Remove Item\n";
        cout << "3. Search Item\n";
        cout << "4. Display All Items\n";
        cout << "5. Exit\n";
        cout << "Enter your choice: ";
        cin >> choice;

        switch (choice) {
            case 1:
                cout << "Enter item to add: ";
                cin >> item;
                shoppingList.push_back(item);
                cout << "Item added successfully!\n";
                break;

            case 2: {
                cout << "Enter item to remove: ";
                cin >> item;
                bool found = false;

                for (int i = 0; i < shoppingList.size(); i++) {
                    if (shoppingList[i] == item) {
                        shoppingList.erase(shoppingList.begin() + i);
                        cout << "Item removed successfully!\n";
                        found = true;
                        break;
                    }
                }

                if (!found)
                    cout << "Item not found!\n";
                break;
            }

            case 3: {
                cout << "Enter item to search: ";
                cin >> item;
                bool found = false;

                for (string x : shoppingList) {
                    if (x == item) {
                        found = true;
                        break;
                    }
                }

                if (found)
                    cout << "Item found!\n";
                else
                    cout << "Item not found!\n";
                break;
            }

            case 4:
                cout << "\nShopping List:\n";

                if (shoppingList.empty()) {
                    cout << "List is empty.\n";
                } else {
                    for (string x : shoppingList)
                        cout << x << endl;
                }
                break;

            case 5:
                cout << "Exiting Shopping List.\n";
                break;

            default:
                cout << "Invalid choice!\n";
        }

    } while (choice != 5);

    return 0;
}

