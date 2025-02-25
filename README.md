#include <stdio.h>



// Estrutura para armazenar os dados de cada cidade
struct Carta {
    char estado[20];  // Nome do estado (A a H)
    int cidade;       // Número da cidade (1 a 4)
    int populacao;    // População da cidade
    float area;       // Área da cidade em km²
    float pib;        // PIB da cidade em bilhões
    int pontos_turisticos;  // Número de pontos turísticos
};

void cadastrarCidades(struct Carta *carta, const char *estado) {
    for (int i = 0; i < 4; i++) {
        carta[i].cidade = i + 1;
        snprintf(carta[i].estado, sizeof(carta[i].estado), "%s", estado);
        
        printf("\nCidade %d do %s:\n", carta[i].cidade, estado);
        printf("Informe a população: ");
        scanf("%d", &carta[i].populacao);
        
        printf("Informe a área: ");
        scanf("%f", &carta[i].area);
        
        printf("Informe o PIB: ");
        scanf("%f", &carta[i].pib);
        
        printf("Informe o número de pontos turísticos: ");
        scanf("%d", &carta[i].pontos_turisticos);
    }
}

void exibirCidades(struct Carta *carta) {
    for (int i = 0; i < 4; i++) {
        printf("\nCidade %d do %s:\n", carta[i].cidade, carta[i].estado);
        printf("População: %d\n", carta[i].populacao);
        printf("Área: %.2f km²\n", carta[i].area);
        printf("PIB: %.2f bilhões\n", carta[i].pib);
        printf("Pontos turísticos: %d\n", carta[i].pontos_turisticos);
    }
}

int main() {
    struct Carta carta1[4], carta2[4];

    printf("Cadastro das Cidades do Estado A:\n");
    cadastrarCidades(carta1, "Estado A");
    
    printf("\nCadastro das Cidades do Estado B:\n");
    cadastrarCidades(carta2, "Estado B");

    printf("\nDados Cadastrados:\n");
    exibirCidades(carta1);
    exibirCidades(carta2);

    return 0;
}
