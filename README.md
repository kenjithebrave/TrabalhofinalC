# TrabalhofinalC
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <math.h>

struct VEICULOS{
	char nome[30];
	char tipo[30];
	float valor, IPVA_DESCONTO, IPVA;
	int pagamento;
	int opcaoVeiculo;
};

void listar();
void header();
void cadastrar();

int main(){
	char opc;
	header();
	
	printf("[C]alcular IPVA de um veiculo informado\n");
	printf("[V]isualizar Relatorio de veiculos com IPVA calculados\n");
	printf("[E]quipe\n");
	printf("[S]air do sistema\n\n");

	printf("Declare qual das opcoes acima deseja executar: ");
	scanf("%c", &opc);
	
	if(opc == 's' || opc == 'S'){
		header();
		printf("Saindo do sistema...\n");
	
	}
	
	while(opc != 'S' && opc != 's'){
		switch(opc){
		case 'C':
		case 'c':
			cadastrar();
		break;
		case 'V':
		case 'v': 
			listar();
		break;
		case 'E':
		case 'e':
			header();
			printf("Desenvolvedores responsáveis:\n");
			printf("Atividade avaliativa de Programacao Estruturada\n\n");
			printf(" - Silas Kenji de Souza Otsuka\n");
			printf(" - Pablo de Lima Veiga\n\n");
		
			system("pause");
		break;
		
		default:
			header();
			printf("ERRO\nOpcao invalida\n");
			system("pause");

	}
	fflush(stdin);
	header();
		
	printf("[C]alcular IPVA de um veiculo informado\n");
	printf("[V]isualizar relatorio de veiculos com IPVA calculados\n");
	printf("[E]quipe\n");
	printf("[S]air do sistema\n\n");

	printf("Declare qual das opcoes acima deseja executar: ");
	scanf("%c", &opc);
	if(opc == 's' || opc == 'S'){
		header();
		printf("Saindo do sistema...\n");
		
	}
	}
		
}

void header(){
	system("cls");
	
	printf("-------------------------------\n");
	printf("         CALCULO DO IPVA       \n");
	printf("-------------------------------\n\n");
}

void cadastrar(){
	struct VEICULOS veiculo;
	header();
	
	FILE *arq;
	
	arq = fopen("arquivo.txt", "a");
	
	if(arq == NULL){
		printf("Arquivo nao foi encontrado.");
	} else {
		printf("[1] MOTO\n");
		printf("[2] CARRO\n");
		printf("[3] ONIBUS\n");
		printf("[4] CAMINHAO\n\n");
		
		printf("Diante das opcoes citadas acima, informe de qual tipo o seu veiculo corresponde: ");
		
		scanf("%d", &veiculo.opcaoVeiculo);
		
		switch(veiculo.opcaoVeiculo){
			case 1:
				
				fflush(stdin);
				printf("Informe o nome do veiculo (sem espaco):");
				fgets(veiculo.nome, 20, stdin);  
				
				printf("Informe o valor do veiculo na tabela FIPE (R$ 99.99):\n");
				scanf("%f", &veiculo.valor);
				
				veiculo.IPVA = veiculo.valor*0.025;
				
				header();
				
				printf("Veiculo: Moto\n");
				printf("Nome: %s", veiculo.nome);
				printf("Valor: %.2f\n", veiculo.valor);
				printf("Valor do seu IPVA -  R$%.2f\n\n", veiculo.IPVA);
					
				printf("Formas de pagamento: \n");
				printf("[1] a vista\n");
				printf("[2] parcelado em 3x\n\n");
				
				printf("Selecione o metodo de pagamento: ");
				
				scanf("%d", &veiculo.pagamento);
				
				if(veiculo.pagamento == 1){
					veiculo.IPVA_DESCONTO = veiculo.IPVA - (veiculo.IPVA * 0.07);
				}
				
				printf("\n\n-- Operação bem sucedida --\n\n");
// Aqui pensei em colocar operação finalizada porém achei que poderia ficar confuso
				system("pause");
				

			break;
			case 2:
				
				fflush(stdin);
					printf("Informe o nome do veiculo (sem espaco):");
				fgets(veiculo.nome, 20, stdin);  
				
				printf("Informe o valor do veiculo na tabela FIPE (R$ 99.99):\n");
				scanf("%f", &veiculo.valor);
				
				veiculo.IPVA = veiculo.valor*0.03;
			
				header();
				printf("Veiculo: Carro\n");
				printf("Nome: %s\n", veiculo.nome);
				printf("Valor: %f\n", veiculo.valor);
				printf("Valor do seu IPVA - R$%.2f\n\n", veiculo.IPVA);
					
				printf("Formas de pagamento: \n");
				printf("[1] a vista\n");
				printf("[2] parcelado em 3x\n");
				
				printf("Escolha a forma de pagamento: ");
				
				scanf("%d", &veiculo.pagamento);
				
				if(veiculo.pagamento == 1){
					veiculo.IPVA_DESCONTO = veiculo.IPVA - (veiculo.IPVA * 0.07);
				}
			
				printf("\n\n---- Operação bem sucedida ----\n\n");
				
				system("pause");
			

			break;
			
			case 3:
				
				fflush(stdin);
					printf("Informe o nome do veiculo (sem espaco):");
				fgets(veiculo.nome, 20, stdin);  
				
				printf("Informe o valor do veiculo na tabela FIPE (R$ 99.99):\n");
				scanf("%f", &veiculo.valor);
				
				veiculo.IPVA = veiculo.valor*0.01;
				
				header();
				printf("Veiculo: Onibus\n");
				printf("Nome: %s\n", veiculo.nome);
				printf("Valor: %f\n", veiculo.valor);
				printf("Valor do seu IPVA - R$%.2f\n\n", veiculo.IPVA);
					
				printf("Formas de pagamento: \n");
				printf("[1] a vista\n");
				printf("[2] parcelado em 3x\n");
				
				printf("Escolha a forma de pagamento: ");
				
				scanf("%d", &veiculo.pagamento);
				
				if(veiculo.pagamento == 1){
					veiculo.IPVA_DESCONTO = veiculo.IPVA - (veiculo.IPVA * 0.07);
				}
				
				printf("\n\n---- Operacao bem sucedida ----\n\n");
				
				system("pause");
			

			break;
			
			case 4:
			
				fflush(stdin);
					printf("Informe o nome do veiculo (sem espaco):");
				fgets(veiculo.nome, 20, stdin);  
				
				printf("Informe o valor do veiculo na tabela FIPE (R$ 99.99):\n");
				scanf("%f", &veiculo.valor);
				
				veiculo.IPVA = veiculo.valor*0.01;
				
				header();
				printf("Veiculo: Caminhao");
				printf("Nome: %s\n", veiculo.nome);
				printf("Valor: %f\n", veiculo.valor);
				printf("Valor do seu IPVA  R$%.2f\n\n", veiculo.IPVA);
					
				printf("Formas de pagamento: \n");
				printf("[1] a vista\n");
				printf("[2] parcelado em 3x:\n");
				
				printf("Escolha a forma de pagamento: ");
				
				scanf("%d", &veiculo.pagamento);
				
				if(veiculo.pagamento == 1){
					veiculo.IPVA_DESCONTO = veiculo.IPVA - (veiculo.IPVA * 0.07);
				}
				
				printf("\n\n-- Operacao bem sucecida --\n\n");
				
				system("pause");
				

			break;
		}
			fwrite(&veiculo, sizeof(struct VEICULOS), 1, arq);
			fclose(arq);
	}
}

void listar(){
	struct VEICULOS veiculo;
	header();
	FILE *arq;
	
	arq = fopen("arquivo.txt", "r");
	
	if(arq == NULL){
		printf("Arquivo nao encontrado");
	} else {
		printf("VISUALIZANDO RELATORIO COMPLETO COM CALCULOS DE IPVA\n\n");
		
		while(fread(&veiculo, sizeof(struct VEICULOS), 1, arq) == 1){
			printf("-----------------------------------------------\n");
			if(veiculo.opcaoVeiculo == 1) printf("Tipo: Moto\n");
			if(veiculo.opcaoVeiculo == 2) printf("Tipo: Carro\n");
			if(veiculo.opcaoVeiculo == 3) printf("Tipo: Onibus\n");
			if(veiculo.opcaoVeiculo == 4) printf("Tipo: Caminhao\n");
			printf("Veiculo: %s\n", veiculo.nome);
			printf("Valor: R$%.2f\n", veiculo.valor);
			printf("Valor do IPVA: %.2f\n\n", veiculo.IPVA);
			if(veiculo.pagamento == 1){
				printf("Forma de pagamento: a vista\n");
				printf("Valor do IPVA com desconto: %.2f\n", veiculo.IPVA_DESCONTO);
			} else {
				printf("Forma de pagamento: parcelado 3x\n");
				printf("3 parcelas de R$ %.2f\n", veiculo.IPVA/3);
			}
		
		}
		
	}
	fclose(arq);
		printf("-----------------------------------------------\n");
	system("pause");
	
}

