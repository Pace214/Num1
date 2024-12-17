#include <stdio.h>
#include <stdlib.h>
#include <math.h>
//Αλέξανδρος Περουσάκης 1117202400168
// Συνάρτηση για να ελέγξουμε αν ένας αριθμός είναι πρώτος
int is_prime(int num) {
    if (num <= 1) {
        return 0; // Δεν είναι πρώτος
    }
    if (num == 2) {
        return 1; // Το 2 είναι πρώτος
    }
    if (num % 2 == 0) {
        return 0; // Κανένας άρτιος αριθμός εκτός του 2 δεν είναι πρώτος
    }

    // Ελέγχουμε για αριθμούς από 3 μέχρι την τετραγωνική ρίζα του num
    for (int i = 3; i <= sqrt(num); i += 2) {
        if (num % i == 0) {
            return 0; // Δεν είναι πρώτος
        }
    }
    return 1; // Είναι πρώτος
}

int main() {
    int arth;

    // Ζητάμε από τον χρήστη να εισάγει έναν θετικό αριθμό N
    printf("Dose arithmo: ");
    scanf("%d", &arth);

    // Επαναλαμβάνουμε αν ο αριθμός είναι μικρότερος ή ίσος με 0
    while (arth <= 0) {
        printf("H timh den einai egkiri. Dose xana arithmo: ");
        scanf("%d", &arth);
    }

    int metritis = 0; // Μετρητής πρώτων αριθμών
    int num = 10;  // Ξεκινάμε από το 10, το πρώτο 2ψήφιο αριθμό

    // Εντολή για την εμφάνιση των πρώτων N αριθμών
    printf("Oi prwtoi %d prwtoi arithmoi me toylaxisti dyo psifia einai:\n", arth);

    while (metritis < arth) {
        if (is_prime(num)) {
            printf("%d\n", num);
            metritis++;
        }
        num++;
    }

    return 0;
}
