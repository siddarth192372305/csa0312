#include <stdio.h>
#include <stdlib.h>

typedef struct {
    int u, v, weight;
} Edge;

int compare(const void *a, const void *b) {
    return ((Edge *)a)->weight - ((Edge *)b)->weight;
}

void kruskal(Edge edges[], int numEdges, int numVertices) {
    qsort(edges, numEdges, sizeof(Edge), compare);
    // Further implementation for union-find and MST construction goes here
}

int main() {
    // Example usage
    Edge edges[] = { {0, 1, 10}, {0, 2, 6}, {0, 3, 5}, {1, 3, 15}, {2, 3, 4} };
    int numEdges = sizeof(edges) / sizeof(edges[0]);
    int numVertices = 4;

    kruskal(edges, numEdges, numVertices);
    return 0;
}
