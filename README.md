# Atividade-03--JAVA

package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio01 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite um número inteiro N: ");
        int n = leitor.nextInt();

        if (n < 1) {
            System.out.println("Não há valores a exibir.");
        } else {
            int i = 1;
            while (i <= n) {
                System.out.println(i);
                i++;
            }
        }

        leitor.close();
    }
}



package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio02 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite um número inteiro para a tabuada: ");
        int numero = leitor.nextInt();

        int i = 1;
        while (i <= 10) {
            System.out.println(numero + " x " + i + " = " + (numero * i));
            i++;
        }

        leitor.close();
    }
}


package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio03 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        double nota;
        do {
            System.out.print("Digite uma nota entre 0 e 10: ");
            nota = leitor.nextDouble();

            if (nota < 0 || nota > 10) {
                System.out.println("Valor inválido! Tente novamente.");
            }
        } while (nota < 0 || nota > 10);

        System.out.printf("Nota aceita: %.2f%n", nota);

        leitor.close();
    }
}

package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio04 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        int opcao;
        do {
            System.out.println("\n--- MENU DE OPÇÕES ---");
            System.out.println("1 - Dobro");
            System.out.println("2 - Metade");
            System.out.println("3 - Quadrado");
            System.out.println("0 - Sair");
            System.out.print("Escolha uma opção: ");
            opcao = leitor.nextInt();

            switch (opcao) {
                case 1 -> {
                    System.out.print("Digite um número: ");
                    double num = leitor.nextDouble();
                    System.out.println("Dobro: " + (num * 2));
                }
                case 2 -> {
                    System.out.print("Digite um número: ");
                    double num = leitor.nextDouble();
                    System.out.println("Metade: " + (num / 2));
                }
                case 3 -> {
                    System.out.print("Digite um número: ");
                    double num = leitor.nextDouble();
                    System.out.println("Quadrado: " + (num * num));
                }
                case 0 -> System.out.println("Saindo do programa...");
                default -> System.out.println("Opção inválida! Tente novamente.");
            }
        } while (opcao != 0);

        leitor.close();
    }
}

package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio05 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite o valor de A: ");
        int a = leitor.nextInt();

        System.out.print("Digite o valor de B: ");
        int b = leitor.nextInt();

        if (a > b) {
            System.out.println("Intervalo inválido! O valor de A deve ser menor ou igual a B.");
        } else {
            int somaPares = 0;
            for (int i = a; i <= b; i++) {
                if (i % 2 == 0) {
                    somaPares += i;
                }
            }
            System.out.println("A soma dos números pares no intervalo de " + a + " a " + b + " é: " + somaPares);
        }

        leitor.close();
    }
}


package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio06 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite um número inteiro não negativo: ");
        int numero = leitor.nextInt();

        if (numero < 0) {
            System.out.println("Entrada inválida! O número deve ser não negativo.");
        } else {
            long fatorial = 1; // Usando long para suportar fatoriais maiores
            for (int i = 1; i <= numero; i++) {
                fatorial *= i;
            }
            System.out.println("O fatorial de " + numero + " é: " + fatorial);
        }

        leitor.close();
    }
}

package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio07 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite a quantidade de alunos da turma: ");
        int qtdAlunos = leitor.nextInt();

        if (qtdAlunos <= 0) {
            System.out.println("Quantidade de alunos inválida.");
        } else {
            double somaNotas = 0;
            int aprovados = 0;
            int reprovados = 0;

            for (int i = 1; i <= qtdAlunos; i++) {
                System.out.print("Digite a nota do aluno " + i + ": ");
                double nota = leitor.nextDouble();
                somaNotas += nota;

                if (nota >= 6.0) {
                    aprovados++;
                } else {
                    reprovados++;
                }
            }

            double mediaTurma = somaNotas / qtdAlunos;

            System.out.printf("Média da turma: %.2f%n", mediaTurma);
            System.out.println("Alunos com nota >= 6.0: " + aprovados);
            System.out.println("Alunos com nota < 6.0: " + reprovados);
        }

        leitor.close();
    }
}


package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio08 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite um valor inteiro (0 para encerrar): ");
        int valor = leitor.nextInt();

        if (valor == 0) {
            System.out.println("Nenhum valor foi lido.");
        } else {
            int quantidade = 0;
            int soma = 0;
            int maior = valor;
            int menor = valor;

            while (valor != 0) {
                quantidade++;
                soma += valor;

                if (valor > maior) {
                    maior = valor;
                }
                if (valor < menor) {
                    menor = valor;
                }

                System.out.print("Digite o próximo valor inteiro (0 para encerrar): ");
                valor = leitor.nextInt();
            }

            System.out.println("Quantidade de valores lidos: " + quantidade);
            System.out.println("Soma dos valores: " + soma);
            System.out.println("Maior valor: " + maior);
            System.out.println("Menor valor: " + menor);
        }

        leitor.close();
    }
}



package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio09 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        System.out.print("Digite um número N (de 1 a 9): ");
        int n = leitor.nextInt();

        if (n < 1 || n > 9) {
            System.out.println("Entrada inválida! O número deve estar entre 1 e 9.");
        } else {
            for (int i = 1; i <= n; i++) {
                System.out.println("--- TABUADA DO " + i + " ---");
                for (int j = 1; j <= 10; j++) {
                    System.out.println(i + " x " + j + " = " + (i * j));
                }
                System.out.println(); // Linha em branco separando as tabuadas
            }
        }

        leitor.close();
    }
}



package br.com.seunome.lista03;

import java.util.Scanner;

public class Exercicio10 {
    public static void main(String[] args) {
        Scanner leitor = new Scanner(System.in);

        double totalCompra = 0.0;
        int quantidadeItens = 0;

        System.out.print("Digite o código do produto (0 para finalizar): ");
        int codigo = leitor.nextInt();

        while (codigo != 0) {
            System.out.print("Digite o preço unitário do produto: R$ ");
            double precoUnitario = leitor.nextDouble();

            System.out.print("Digite a quantidade do produto: ");
            int quantidade = leitor.nextInt();

            totalCompra += (precoUnitario * quantidade);
            quantidadeItens += quantidade;

            System.out.print("\nDigite o código do próximo produto (0 para finalizar): ");
            codigo = leitor.nextInt();
        }

        if (quantidadeItens == 0) {
            System.out.println("Nenhum produto foi cadastrado.");
        } else {
            System.out.println("\n--- FINALIZAÇÃO DA COMPRA ---");
            System.out.println("Formas de pagamento:");
            System.out.println("1 - Dinheiro (5% de desconto)");
            System.out.println("2 - Débito (sem alteração)");
            System.out.println("3 - Crédito (3% de acréscimo)");
            System.out.print("Escolha a forma de pagamento: ");
            int formaPagamento = leitor.nextInt();

            double totalFinal = totalCompra;

            switch (formaPagamento) {
                case 1 -> totalFinal = totalCompra * 0.95; // 5% de desconto
                case 2 -> totalFinal = totalCompra;        // sem alteração
                case 3 -> totalFinal = totalCompra * 1.03; // 3% de acréscimo
                default -> System.out.println("Forma de pagamento inválida. O total permanece sem alteração.");
            }

            // IFS INDEPENDENTES
            if (totalFinal > 300.00) {
                System.out.println("Aviso: Compra grande.");
            }
            if (quantidadeItens > 20) {
                System.out.println("Aviso: Muitos itens.");
            }

            System.out.printf("Total de itens comprados: %d%n", quantidadeItens);
            System.out.printf("Total final a pagar: R$ %.2f%n", totalFinal);
        }

        leitor.close();
    }
}


