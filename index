//Leonardo de Oliveira Florindo, Pedro Henrique do Divino Sandrini, Igor Henrique dos Santos, Rodrigo Aparecido Roza, Bruno Elias Avelar, Renato Canelossi Inacio. 
#include <stdio.h>
struct boletim {
    float notas[2][2];
    float media;
    int passou;
    
};
struct alunos {
   char nome[50];
    int serie;
   struct boletim b;
};

    struct alunos lerAlunos(int numAluno){
        struct alunos aluno;
     
        printf("\nInsira o nome do aluno %d: ", numAluno +1);
        scanf("%s",&aluno.nome);
        printf("Insira a serie do aluno %d: ", numAluno +1);
        scanf("%d",&aluno.serie);
        
        return aluno;
    }
    struct boletim lerNotas(){
        struct boletim boletimAluno;
        
        for(int linha=0; linha<2; linha++){
            for(int coluna=0; coluna<2; coluna++){
                do{
                    printf(
                        "Insira a %s nota de %s: ",
                        coluna == 0 ? "primeira" : "segunda",
                        linha == 0 ? "trabalho" : "prova"
                    );
                    
                    scanf("%f", &boletimAluno.notas[linha][coluna]);
                } while (
                    boletimAluno.notas[linha][coluna] < 0 ||
                    boletimAluno.notas[0][coluna] > 2 ||
                    boletimAluno.notas[1][coluna] > 3 
                );
            } 
        }
    
        return boletimAluno;
    }
 float calcularMedia(struct boletim b){
    float soma= 0;
    
    for(int linha=0; linha<2; linha++){
        for(int coluna=0; coluna<2; coluna++){
            soma += b.notas[linha][coluna]; 
        } 
    }
    return soma;
 };
 int validarPassou(struct boletim b){
     return b.media >= 6 ? 1 : 0;
 };
void mostraAlunos(struct alunos aluno){
    printf("\nO aluno: %s\nDa serie: %d", aluno.nome, aluno.serie);   
    if (aluno.b.passou == 1){
        printf("\nO aluno PASSOU com media %.1f", aluno.b.media);
    } else {
        printf("\nO aluno REPROVOU com media %.1f", aluno.b.media);
    }
};

int main(){
    int qtdAlunos = lerQtdAlunos();
    struct alunos aluno[qtdAlunos];

    for(int i=0; i<qtdAlunos; i++){
        aluno[i]=lerAlunos(i);
        aluno[i].b = lerNotas();
        aluno[i].b.media = calcularMedia(aluno[i].b);
        aluno[i].b.passou=validarPassou(aluno[i].b);
    }
    
    for(int i=0; i<qtdAlunos; i++){
        mostraAlunos(aluno[i]);
    }
    
    return 0;
}

int lerQtdAlunos(){
    int qtdAlunos;
    printf("Selecione a quantidade de alunos: ", qtdAlunos);
    scanf("%d",&qtdAlunos);
  return qtdAlunos;
}
