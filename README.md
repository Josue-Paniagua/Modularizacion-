# Modularizacion-
// creo el menu principal para kuego agregar cada mini funcion a este 


class Modularizacion
{

    static void Main()
    {
        int opcion;
        do
        {
            Console.WriteLine("1. Calculadora Básica");
            Console.WriteLine("2. Validación de contraseña");
            Console.WriteLine("3. Números primos");
            Console.WriteLine("4. Suma de números pares");
            Console.WriteLine("5. Conversion de temperaturas ");
            Console.WriteLine("6. Contador de vocales");
            Console.WriteLine("7. Cálculo de factorial");
            Console.WriteLine("8. Juego de adivinanza");
            Console.WriteLine("9. Paso por Referencia");
            Console.WriteLine("10. Tbla de multiplicar ");
            Console.WriteLine("11. Salir");
            Console.Write("Seleccione una opción: ");

            opcion = Convert.ToInt32(Console.ReadLine());

            switch (opcion)
            {
                case 1:
                    CalculadoraB();
                    break;
                case 2:
                    ValidacionC();
                    break;
                case 3:
                    NumerosP();
                    break;
                case 4:
                    SumaP();
                    break;
                case 5:
                    ConversionTem();
                    break;
                case 6:
                    ContadorV();
                    break;
                case 7:
                    CalculoFac();
                    break;
                case 8:
                    JuegoAdi();
                    break;
                case 9:
                    PasoRef();
                    break;
                case 10:
                    Tablas();
                    break;
                case 11:
                    Console.WriteLine("Adiós");
                    break;
                default:
                    Console.WriteLine("Vea las opciones del menu y presione un número válido.");
                    break;
            }

        } while (opcion != 11);
    }
    //AQUI AGREGARE LA FUNCION 1 DE AL CALCULADORA BASICA 
    static void CalculadoraB()
    {
        int suma, multi, opcion;
        float div, resta, num1, num2, resultado;
        Console.Write("Ingrese el primer número: ");
        if (!float.TryParse(Console.ReadLine(), out num1))
        {
            Console.WriteLine("Error: Número no válido.");
            return;
        }

        Console.Write("Ingrese el segundo número: ");
        if (!float.TryParse(Console.ReadLine(), out num2))
        {
            Console.WriteLine("Error: Número no válido.");
            return;
        }

        Console.WriteLine("Ingrese una opcion");
        Console.WriteLine("1. Suma");
        Console.WriteLine("2. Resta");
        Console.WriteLine("3. Multiplicación");
        Console.WriteLine("4. División");
        opcion = Convert.ToInt32(Console.ReadLine());

        switch (opcion)
        {
            case 1:
                Console.WriteLine("Suma");
                resultado = num1 + num2;
                break;
            case 2:
                Console.WriteLine("Resta");
                resultado = num1 - num2;
                break;
            case 3:
                Console.WriteLine("Multiplicación");
                resultado = num1 * num2;
                break;
            case 4:
                Console.WriteLine("División");
                resultado = num1 / num2;
                break;
            default:
                Console.WriteLine("Opción no válida");
                return;


        }
        Console.WriteLine("El resultado en abse a lo que usted escogio es : " + resultado);
    }

    //AQUI AGREGARE LA FUNCION 2 DE VALIDACION DE CONTRASEÑA
    static void ValidacionC()
    {
        string contraseña = "1234";
        string contraBuena;
        do
        {
            Console.WriteLine("Ingrese la contraseña ");
            contraBuena = Console.ReadLine();

            if (contraBuena != contraseña)
            { Console.WriteLine("Esa contraseña es incorrecta, vuelva  a intentar "); }

        }
        while (contraBuena != contraseña);
        Console.WriteLine(" *Acceso concedido*");
    }
    //funcion para saber si un numero es primo 
    static bool Primo(int n)
    {
        if (n < 2) return false;

        for (int i = 2; i <= Math.Sqrt(n); i++)
        {
            if (n % i == 0)
                return false;
        }
        return true;

    }

    //AQUI AGREGARE LA FUNCION 3 DE NUMEROS PRIMOS
    static void NumerosP()
    {
        Console.WriteLine("Ingrese un numero entero : ");
        if (!int.TryParse(Console.ReadLine(), out int num))
        {
            Console.WriteLine("Eso que ustd ingreso no es valido ");
            return;
        }
        if (Primo(num))
            Console.WriteLine(+num + " Es un numero primo ");
        else
            Console.WriteLine(+num + " NO es un numero primo ");
    }
    static void SumaP()
    {
        int n1 = 0, suma = 0;

        while (true)
        {
            Console.WriteLine("Ingrese un número entero (Ingrese 0 para terminar): ");
            n1 = Convert.ToInt32(Console.ReadLine());

            if (n1 == 0)
            {
                break;
            }

            if (n1 % 2 == 0)
            {
                suma += n1;
            }
        }

        Console.WriteLine("La suma de los números pares ingresados es: " + suma);
    }

    static void ConversionTem()
    {

        int opcion;
        double tempe, resul;

        Console.WriteLine("1. Convertir de celsius a fahrenheit ");
        Console.WriteLine("2. Convertir de fahrenheit a celsius ");
        if (!int.TryParse(Console.ReadLine(), out opcion))
        {
            Console.WriteLine("Su cantidad no es valdia ");
            return;
        }
        Console.WriteLine("Ingrese la temperatura a convertir : ");
        if (!double.TryParse(Console.ReadLine(), out tempe))
        {
            Console.WriteLine("Su cantidad no es valdia ");
            return;
        }

        switch (opcion)
        {
            case 1:
                resul = (tempe * 9 / 5) + 32;
                Console.WriteLine("La temperatura en celsius a fahrenheir es de " + resul);
                break;
            case 2:
                resul = (tempe - 32) * 5 / 9;
                Console.WriteLine("La tempertura en Fahrenheit a celsius  es  de : " + resul);
                break;
            default:
                Console.WriteLine("Esa opcion o esta vlaida en este sistma ");
                break;
        }

    }

    static void ContadorV()
    {
        string cadena;
        int contador = 0;

        Console.Write("Ingrese una frase o texto: ");
        cadena = Console.ReadLine(); 

        for (int i = 0; i < cadena.Length; i++)
        {
            char letra = char.ToLower(cadena[i]);

            if (letra == 'a' || letra == 'e' || letra == 'i' || letra == 'o' || letra == 'u')
            {
                contador++;
            }
        }

        Console.WriteLine($"La cantidad de vocales en la frase es: {contador}");
    }

    static void CalculoFac()
    {
        int num1;
        long factorial = 1; 

        Console.Write("Ingrese un número entero: ");
        if (!int.TryParse(Console.ReadLine(), out num1) || num1 < 0)
        {
            Console.WriteLine("Error: Debe ingresar un número entero positivo.");
            return;
        }

        for (int i = 1; i <= num1; i++)
        {
            factorial *= i;
        }

        Console.WriteLine($"El factorial de {num1} es: {factorial}");
    }

    static void JuegoAdi()
    {
        Random aleatorio = new Random();
        int numeroAle = aleatorio.Next(1, 101);
        int intento;
        int intentoRealizado = 0;

        Console.WriteLine("Adivina el número entre 1 y 100");

        do
        {
            Console.Write("Introduce un numero");
            if (!int.TryParse(Console.ReadLine(), out intento))
            {
                Console.WriteLine("Eso no es un numero valido");
                continue;
            }
            intentoRealizado++;
            if (intento < numeroAle)
            {
                Console.WriteLine("Demasiado bajo");
            }
            else if (intento > numeroAle)
            {
                Console.WriteLine("Demasiado alto");
              
            }
            else
            {
                Console.WriteLine("fELICIDADES HAS ADIVINADO EL NUMERO EN " + intentoRealizado +"Intentos ");
            }
            
                    }
        while (intento != numeroAle);

    }

    // Funcion por aparte para el intercambio de valores
    static void Intercambiar(ref int a, ref int b)
    {
        int temp = a;
        a = b;
        b = temp;
    }

    static void PasoRef() 
    {
        int num1, num2;
        
        Console.Write("Ingrese el primer número: ");
        while (!int.TryParse(Console.ReadLine(), out num1))
        {
            Console.WriteLine("Error: Ingrese un número entero válido.");
            Console.Write("Ingrese el primer número: ");
        }

        Console.Write("Ingrese el segundo número: ");
        while (!int.TryParse(Console.ReadLine(), out num2))
        {
            Console.WriteLine("Error: Ingrese un número entero válido.");
            Console.Write("Ingrese el segundo número: ");
        }

        Console.WriteLine($"\nValores originales: num1 = {num1}, num2 = {num2}");

        Intercambiar(ref num1, ref num2);

        Console.WriteLine($"Valores intercambiados: num1 = {num1}, num2 = {num2}\n");
    }

    static void Tablas()
    {
        int num1, resultado;

        Console.Write("Ingrese un numero del cual quiera saber su tabla del 1 al 10 : ");
        if (!int.TryParse(Console.ReadLine(), out num1))
        {
            Console.WriteLine("Ese numero no es valido, vuela a intenar ");
            Console.WriteLine("Ingrese el numero de nuevo");
            num1 = Convert.ToInt32(Console.ReadLine());
        }
        Console.WriteLine($"La tabla de multiplicar del  {num1}:");

        for (int i = 1; i <= 10; i++)
        {
            resultado = num1 * i;
            Console.WriteLine($" {num1} x {i} = {resultado}");

        }




    }
        
    
    }

