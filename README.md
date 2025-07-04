#include <stdio.h>
#include <stdlib.h>

// Compare function for descending order
int compare(const void *a, const void *b) {
    return (*(int*)b - *(int*)a);
}

int main() {
    int n;
    scanf("%d", &n);
    
    int a[n];
    
    for(int i = 0; i < n; i++) {
        scanf("%d", &a[i]);
    }
    
    // Sort in descending order
    qsort(a, n, sizeof(int), compare);
    
    int maxTeamSize = n < 6 ? n : 6;
    int sum = 0;
    
    for(int i = 0; i < maxTeamSize; i++) {
        sum += a[i];
    }
    
    printf("%d\n", sum);
    
    return 0;
}
