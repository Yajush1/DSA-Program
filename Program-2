#include <iostream>
#include <cstdlib> // For malloc and free
using namespace std;

// Define the structure of a node in the linked list
struct Node {
    int data;
    Node* next;
};

// Function to insert a node at the beginning
void insertAtBeginning(Node*& head, int value) {
    // Allocate memory using malloc
    Node* newNode = (Node*)malloc(sizeof(Node));
    if (newNode == nullptr) {
        cout << "Memory allocation failed!" << endl;
        return;
    }
    newNode->data = value;
    newNode->next = head;
    head = newNode;
    cout << "Inserted " << value << " at the beginning.\n";
}

// Function to insert a node at the end
void insertAtEnd(Node*& head, int value) {
    // Allocate memory using malloc
    Node* newNode = (Node*)malloc(sizeof(Node));
    if (newNode == nullptr) {
        cout << "Memory allocation failed!" << endl;
        return;
    }
    newNode->data = value;
    newNode->next = nullptr;

    if (head == nullptr) {
        head = newNode;
        cout << "Inserted " << value << " at the end (it's the first node).\n";
        return;
    }

    Node* temp = head;
    while (temp->next != nullptr) {
        temp = temp->next;
    }
    temp->next = newNode;
    cout << "Inserted " << value << " at the end.\n";
}

// Function to delete a node from the beginning
void deleteFromBeginning(Node*& head) {
    if (head == nullptr) {
        cout << "List is empty. Cannot delete.\n";
        return;
    }
    Node* temp = head;
    head = head->next;
    free(temp); // Free the memory allocated for the node
    cout << "Node deleted from the beginning.\n";
}

// Function to delete a node from a specific position
void deleteFromPosition(Node*& head, int position) {
    if (head == nullptr) {
        cout << "List is empty. Cannot delete.\n";
        return;
    }
    if (position == 0) {
        deleteFromBeginning(head);
        return;
    }
    Node* temp = head;
    for (int i = 0; temp != nullptr && i < position - 1; i++) {
        temp = temp->next;
    }
    if (temp == nullptr || temp->next == nullptr) {
        cout << "Position is out of range.\n";
        return;
    }
    Node* nodeToDelete = temp->next;
    temp->next = temp->next->next;
    free(nodeToDelete); // Free the memory allocated for the node
    cout << "Node deleted from position " << position << ".\n";
}

// Function to display the list
void displayList(Node* head) {
    if (head == nullptr) {
        cout << "List is empty.\n";
        return;
    }
    Node* temp = head;
    cout << "List: ";
    while (temp != nullptr) {
        cout << temp->data << " ";
        temp = temp->next;
    }
    cout << endl;
}

// Main function to demonstrate insertion and deletion operations
int main() {
    Node* head = nullptr; // Initially, the list is empty

    // Display the list initially (it will be empty)
    displayList(head);

    // Insert nodes at the beginning
    insertAtBeginning(head, 10);
    insertAtBeginning(head, 20);
    insertAtBeginning(head, 30);
    displayList(head);

    // Insert nodes at the end
    insertAtEnd(head, 40);
    insertAtEnd(head, 50);
    displayList(head);

    // Delete node from the beginning
    deleteFromBeginning(head);
    displayList(head);

    // Delete node from a specific position
    deleteFromPosition(head, 2); // Delete node at position 2 (0-indexed)
    displayList(head);

    // Try deleting a node from an invalid position
    deleteFromPosition(head, 5); // Position out of range
    displayList(head);

    return 0;
}
