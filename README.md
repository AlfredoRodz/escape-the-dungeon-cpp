# escape-the-dungeon-cpp
#include <iostream>
#include <string>
using namespace std;

int main() {
    string choice;
    int doorChoice;

    // Introduction
    cout << "Welcome to 'Escape the Dungeon'!\n";
    cout << "You awaken in a cold, dark cell with damp stone walls.\n";
    cout << "A flickering torch on the wall casts strange shadows.\n";
    cout << "You must find a way to escape...\n\n";

    // First Decision - Explore or Wait
    cout << "Do you want to (explore) the dungeon or (wait) for help? ";
    cin >> choice;

    // Convert input to lowercase for lenient matching
    for (char& c : choice) c = tolower(c);

    if (choice == "explore") {
        cout << "\nYou sneak out of your cell and find three doors...\n";
        cout << "Door 1: You hear a faint growl.\n";
        cout << "Door 2: It's silent.\n";
        cout << "Door 3: There's a strange humming noise.\n";

        // Input validation loop
        while (true) {
            cout << "\nChoose a door (1, 2, or 3): ";
            cin >> doorChoice;

            if (cin.fail() || doorChoice < 1 || doorChoice > 3) {
                cin.clear();
                cin.ignore(1000, '\n');
                cout << "Invalid input. Please enter 1, 2, or 3.\n";
                continue;
            }
            break;
        }

        // Switch for major decision
        switch (doorChoice) {
            case 1:
                cout << "\nYou open the door and a wild beast attacks!\n";
                cout << "You fight bravely but are defeated.\n";
                break;
            case 2:
                cout << "\nThe door leads to a dark tunnel...\n";
                cout << "You follow it and find an escape hatch. You are free!\n";
                break;
            case 3:
                cout << "\nThe room is filled with magical energy.\n";
                cout << "You are teleported back to your cell. Try again.\n";
                break;
        }

    } else if (choice == "wait") {
        cout << "\nYou wait... and wait...\n";
        cout << "Days pass, and no one comes. You perish in the dungeon.\n";
    } else {
        cout << "\nInvalid choice. You fumble around and attract attention...\n";
        cout << "A guard finds you and locks you up tighter. Game over.\n";
    }

    cout << "\nThanks for playing 'Escape the Dungeon'!\n";
    return 0;
}
