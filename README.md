🍽️ Contador de Almoços Semanais – Linguagem C

Este projeto foi desenvolvido como parte de uma atividade acadêmica com foco no uso de vetores e laços de repetição em linguagem C, simulando o controle de almoços servidos por dia durante uma semana.

🎯 Objetivo

Transformar dados do cotidiano em informações úteis por meio da programação. O projeto utiliza vetores para armazenar e processar os dados de consumo de almoços, permitindo visualizar e analisar a média semanal de forma automatizada.

📌 Tema Escolhido

Consumo de Almoços

Vetor de 7 posições: cada posição representa o total de almoços servidos em um dia da semana.

O programa calcula e exibe a média semanal de almoços servidos.

Apresentação clara e organizada no terminal.

🛠️ Funcionalidades

Entrada dos dados via terminal (um valor por dia).

Cálculo automático da média semanal.

Exibição formatada dos dados e resultados.

Código comentado, indentado e fácil de entender.

💡 Tecnologias e Conceitos Utilizados

Linguagem C

Vetores (arrays)

Laços de repetição (for)

Condicionais (if)

Organização e formatação de dados no terminal

Comentários e boas práticas de programação

📎 Exemplo de Uso
Digite a quantidade de almoços servidos na segunda-feira: 120
Digite a quantidade de almoços servidos na terça-feira: 135
...
Média semanal de almoços servidos: 128.57

✅ Checklist Atendido

 Uso correto de vetor

 Uso de laços de repetição

 Código indentado e comentado

 Saída clara e compreensível

 Testado com diferentes dados

📁 Arquivo

contador_almocos.c: código-fonte principal do projeto.
[main.c](https://github.com/user-attachments/files/22396921/main.c)
#include <stdio.h>

int main() {
    printf("====================================\n");
    printf("         BEM VINDO AO CONTAALMOCO   \n");
    printf(" Monitoramento de almocos - 2 semanas\n");
    printf("====================================\n\n");
    
    // Matriz: 2 semanas x 7 dias 
    int almocos[2][7];
    char *dias[7] = {"Segunda", "Terça", "Quarta", "Quinta", "Sexta", "Sabado", "Domingo"};
    
    int i, j;
    int totalSemana[2] = {0, 0};
    int maior = 0, menor = 99999;
    int semanaMaior = 0, diaMaior = 0;
    int semanaMenor = 0, diaMenor = 0;
    
    // Entrada de dados
    for (i = 0; i < 2; i++) {
        printf("\n--- Semana %d ---\n", i + 1);
        for (j = 0; j < 7; j++) {
            printf("%s: ", dias[j]);
            scanf("%d", &almocos[i][j]);
            
            totalSemana[i] += almocos[i][j];
            
            if (almocos[i][j] > maior) {
                maior = almocos[i][j];
                semanaMaior = i;
                diaMaior = j;
            }
            if (almocos[i][j] < menor) {
                menor = almocos[i][j];
                semanaMenor = i;
                diaMenor = j;
            }
        }
    }
    
    // Relatorio
    printf("\n===================================\n");
    printf("        RELATORIO GERAL             \n");
    printf("===================================\n");
    
    for (i = 0; i < 2; i++) {
        printf("\nSemana %d: \n", i + 1);
        for (j = 0; j < 7; j++) {
            printf("%s: %d almocos\n", dias[j], almocos [i][j]);
        }
        printf("Total da semana %d: %d\n", i + 1, totalSemana[i]);
        printf("Media da semana %d: %.2f\n", i + 1, totalSemana[i] / 7.0);
    }
    
    // Destaques
    printf("\n=================================\n");
    printf("             DESTAQUES            \n");
    printf("=================================\n");
    printf(">> Maior consumo: %s (Semana %d) - %d almocos\n",
            dias[diaMaior], semanaMaior + 1, maior);
    printf(">> Menor consumo: %s (semana %d) - %d almocos\n",
            dias[diaMenor], semanaMenor +1, menor);
            
    // Comparação das semanas
    if (totalSemana[0] > totalSemana[1]) {
        printf("\nSemana  1 foi mais movimentada que a Semana 2.\n");
    } else if (totalSemana[1] > totalSemana[0]) {
        printf("\nSemana  2 foi mais movimentada que a Semana 1.\n");
    } else {
        printf("\nAs duas semanas tiveram o mesmo movimento.\n");
    }
    
    printf("\nObrigado por usar o ContaAlmoco!\n");
    
    return 0;
}

[license..txt](https://github.com/user-attachments/files/22396923/license.txt)MIT License

Copyright (c) 2025 [ Ronaldo Cesar ]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.


