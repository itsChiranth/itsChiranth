#include <stdio.h>
#include <stdlib.h>

struct Clothing {
    int id;
    char name[50];
    float price;
};

void addClothing(struct Clothing *clothing) {
    printf("Enter clothing ID: ");
    scanf("%d", &(clothing->id));
    printf("Enter clothing name: ");
    scanf("%s", clothing->name);
    printf("Enter clothing price: ");
    scanf("%f", &(clothing->price));
    printf("Clothing added successfully!\n");
}

void displayClothing(struct Clothing clothing) {
    printf("ID: %d\n", clothing.id);
    printf("Name: %s\n", clothing.name);
    printf("Price: %.2f\n", clothing.price);
}

int main() {
    int numClothing;
    printf("Enter the number of clothing items: ");
    scanf("%d", &numClothing);

    struct Clothing *clothingItems = (struct Clothing *)malloc(numClothing * sizeof(struct Clothing));

    for (int i = 0; i < numClothing; i++) {
        printf("\nClothing item %d:\n", i + 1);
        addClothing(&clothingItems[i]);
    }

    printf("\n--- Clothing Inventory ---\n");
    for (int i = 0; i < numClothing; i++) {
        printf("\nClothing item %d:\n", i + 1);
        displayClothing(clothingItems[i]);
    }

   return 0;
}

