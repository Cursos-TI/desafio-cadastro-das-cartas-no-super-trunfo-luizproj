#include <stdio.h>

// Definindo a estrutura para representar uma carta
typedef struct {
    char estado;
    char codigo[4]; // Ex: "A01" + '\0'
    char nomeCidade[100];
    int populacao;
    float area;
    float pib;
    int pontosTuristicos;
} Carta;

void lerCarta(Carta *carta, int numero) {
    printf("Digite os dados da Carta %d:\n", numero);

    printf("Estado (A-H): ");
    scanf(" %c", &carta->estado);

    printf("Código da Carta (ex: A01): ");
    scanf("%s", carta->codigo);

    printf("Nome da Cidade: ");
    scanf(" %[^\n]", carta->nomeCidade); // Lê até a quebra de linha

    printf("População: ");
    scanf("%d", &carta->populacao);

    printf("Área (em km²): ");
    scanf("%f", &carta->area);

    printf("PIB (em bilhões de reais): ");
    scanf("%f", &carta->pib);

    printf("Número de Pontos Turísticos: ");
    scanf("%d", &carta->pontosTuristicos);

    printf("\n");
}

void exibirCarta(Carta carta, int numero) {
    printf("Carta %d:\n", numero);
    printf("Estado: %c\n", carta.estado);
    printf("Código: %s\n", carta.codigo);
    printf("Nome da Cidade: %s\n", carta.nomeCidade);
    printf("População: %d\n", carta.populacao);
    printf("Área: %.2f km²\n", carta.area);
    printf("PIB: %.2f bilhões de reais\n", carta.pib);
    printf("Número de Pontos Turísticos: %d\n", carta.pontosTuristicos);
    printf("\n");
}

int main() {
    Carta carta1, carta2;

    // Leitura das cartas
    lerCarta(&carta1, 1);
    lerCarta(&carta2, 2);

    // Exibição das cartas
    exibirCarta(carta1, 1);
    exibirCarta(carta2, 2);

    return 0;
}


