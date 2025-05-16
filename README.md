#include <stdio.h> //biblioteca utilizada
#define MAX_CLIENTES 20
#define MAX_PRODUTOS 20

char clientes[MAX_CLIENTES][50];
char produtos[MAX_PRODUTOS][50];
int total_clientes = 0;
int total_produtos = 0;

void cadastrar_cliente() { //função para adicionar novos clientes ao sistema
    if (total_clientes < MAX_CLIENTES) { //verifica se ainda é possível cadastrar mais produtos
        printf("Nome do cliente: ");
        scanf(" %49[^\n]", clientes[total_clientes]); //lê o nome do cliente, incluindo espaços, até o fim da linha
        printf("Cliente %s cadastrado!\n", clientes[total_clientes]);
        total_clientes++;
    } else {
        printf("Limite de clientes atingido.\n"); //aviso se atingir o limite máximo de clientes cadastrados
    }
}

void cadastrar_produto() { //função para adicionar novos produtos ao sistema
    if (total_produtos < MAX_PRODUTOS) { //verifica se ainda é possível cadastrar mais produtos
        printf("Nome do produto: ");
        scanf(" %49[^\n]", produtos[total_produtos]); //lê o nome do produto, incluindo espaços, até o fim da linha
        printf("Produto %s cadastrado!\n", produtos[total_produtos]);
        total_produtos++;
    } else {
        printf("Limite de produtos atingido.\n"); //aviso se atingir o limite máximo de produtos cadastrados
    }
}

void cadastrar_venda() { //função para registrar uma venda
    char nome_cliente[50];
    char nome_produto[50];
    int quantidade;

    printf("Cliente: ");
    scanf(" %49[^\n]", nome_cliente);
    printf("Produto: ");
    scanf(" %49[^\n]", nome_produto);
    printf("Quantidade: ");
    scanf(" %d", &quantidade);

    printf("Venda registrada! Cliente: %s, Produto: %s, Quantidade: %d\n", nome_cliente, nome_produto, quantidade);
}


void listar_clientes() { //função para listar todos os clientes do sistema
    if (total_clientes == 0) {
        printf("Nenhum cliente cadastrado.\n"); //impressão na tela se não houver nenhum cliente cadastrado
        return;
    }

    printf("Clientes cadastrados:\n");
    for (int i = 0; i < total_clientes; i++) {
        printf("%s\n", clientes[i]); //imprime o nome de cada cliente cadastrado
    }
}

void listar_produtos() { //função para listar todos os produtos do sistema
    if (total_produtos == 0) {  
        printf("Nenhum produto cadastrado.\n"); //impressão na tela se não houver nenhum produto cadastrado
        return;
    }

    printf("Produtos cadastrados:\n");
    for (int i = 0; i < total_produtos; i++) {
        printf("%s\n", produtos[i]); //imprime o nome de cada produto cadastrado
    }
}

int main() {
    int opcao;
    do { //Menu principal que aparece assim que executamos o código
        printf("Bem-vindo ao MENU, o que deseja fazer?:\n");
        printf("1 - Cadastrar Cliente\n");
        printf("2 - Cadastrar Produto\n");
        printf("3 - Cadastrar Venda\n");
        printf("4 - Listar Clientes\n");
        printf("5 - Listar Produtos\n");
        printf("0 - Sair do Sistema\n");
        printf("Opção escolhida: ");
        scanf("%d", &opcao); //Lê a opção dada pelo usuario

//Verifica qual  a opção escolhida pelo usuario e chama a função correspondente
        if (opcao == 1)
            cadastrar_cliente();
        else if (opcao == 2)
            cadastrar_produto();
        else if (opcao == 3)
            cadastrar_venda();
        else if (opcao == 4)
            listar_clientes();
        else if (opcao == 5)
            listar_produtos();
        else if (opcao != 0)
            printf("Opção inválida! Digite outra opção:\n");

    } while (opcao != 0); //Repete o menu até o usuário digitar 0

    printf("Programa encerrado.\n");
    return 0;
}
