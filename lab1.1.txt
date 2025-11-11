#include <stdio.h>
#include <stdlib.h>

#define MAX 100  // Maximum size of stack

int stack[MAX];
int top = -1;  // Stack is empty initially

// Function to push an element into the stack
void push(int value) {
    if (top == MAX - 1) {
        printf("⚠️  Stack Overflow! Cannot push %d\n", value);
    } else {
        top++;
        stack[top] = value;
        printf("✅ Pushed: %d\n", value);
    }
}

// Function to pop an element from the stack
void pop() {
    if (top == -1) {
        printf("⚠️  Stack Underflow! Nothing to pop.\n");
    } else {
        printf("✅ Popped: %d\n", stack[top]);
        top--;
    }
}

// Function to display the stack elements
void display() {
    if (top == -1) {
        printf("📭 Stack is empty.\n");
    } else {
        printf("🧱 Stack elements (top to bottom):\n");
        for (int i = top; i >= 0; i--) {
            printf("%d\n", stack[i]);
        }
    }
}

// Main function
int main() {
    int choice, value;

    while (1) {
        printf("\n--- Stack Operations Menu ---\n");
        printf("1. Push\n");
        printf("2. Pop\n");
        printf("3. Display\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {
            case 1:
                printf("Enter value to push: ");
                scanf("%d", &value);
                push(value);
                break;
            case 2:
                pop();
                break;
            case 3:
                display();
                break;
            case 4:
                printf("🚪 Exiting... Goodbye!\n");
                exit(0);
            default:
                printf("❌ Invalid choice! Try again.\n");
        }
    }

    return 0;
}
