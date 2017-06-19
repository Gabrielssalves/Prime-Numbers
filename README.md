# Prime-Numbers
Basic program for calculating the quantity and the sum of prime numbers in a range. 
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApplication3
{
    class Program
    {
        static void Main(string[] args)
        {
            long numero, divisor, soma = 0, vfinal, vinicial, contagem = 0;
            string confirma;
            int confirma_fim;
            bool primo = false;

            do
            {
                Console.WriteLine("Informe um período apartir de dois números inteiros e positivos para saber quantos números são primos existem nele:\n");

                do
                {
                    Console.WriteLine("Começa em:");
                    vinicial = Convert.ToInt32(Console.ReadLine());
                    Console.WriteLine("\nTermina em:");
                    vfinal = Convert.ToInt32(Console.ReadLine());

                    if (vinicial < 0)
                    {
                        Console.WriteLine("\nVocê inseriu um  número negativo, por favor insira um número inteiro e positivo.\n");
                    }

                    if (vinicial == vfinal)
                    {
                        Console.WriteLine("\nVocê inseriu dois  números repetidos, por favor insira um INTERVALO válido, inteiro e positívo.\n");
                    }

                    } while (vinicial < 0 || vinicial == vfinal);

                for (numero = vinicial; numero <= vfinal; numero = numero + 2)
                {
                    for (divisor = 2; divisor < numero; divisor = divisor + 1)
                    {

                        if ((numero % divisor) == 0)
                        {
                            primo = false;
                            break;
                        }

                        else
                        {
                            primo = true;
                        }
                    }

                    if (primo == true)
                    {
                        contagem++;
                        soma = soma + numero;
                    }

                    primo = false;               


                    if (vinicial == 1)
                    {
                        numero--;
                    }

                    if (numero == 2)
                    {
                        soma = soma + 2;
                        contagem++;
                        numero--;
                    }
                }
               
                Console.WriteLine("\nNeste intervalo existe " + contagem + " números primos.");

                Console.WriteLine("\nCaso queira a soma de todos os primos do intervalo digite 'sim'.\nPara encerrar aperte a tecla 'enter'.\n");
                confirma = Convert.ToString(Console.ReadLine());

                if (confirma == "sim")
                {
                    Console.WriteLine("\nA soma dos números primos do intervalo é igual a:\n " + soma);
                }
                Console.WriteLine("\nDeseja fazer uma nova consulta?\n1 - sim\n2 - não");
                confirma_fim = Convert.ToInt16(Console.ReadLine());

                    if (confirma_fim == 2)
                    {
                        Environment.Exit(1);
                    }
                    soma = 0;
                    contagem = 0;

            } while(confirma_fim == 1);
        }
    }
}

