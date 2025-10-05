package juegonramdon;

import java.util.Random;
import java.util.Scanner;

public class JuegoNRamdon {

    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);
        Random ram = new Random();

        boolean jugarDeNuevo = true;

        while (jugarDeNuevo) {
            System.out.println("**** Bienvenido a Adivina el Numero *****");
            System.out.println("Reglas: Debes adivinar el numero secreto dentro del rango y con un numero limitado de intentos.");

            System.out.println("Selecciona nivel de dificultad:");
            System.out.println("1. Facil (1-10, 5 intentos)");
            System.out.println("2. Medio (1-50, 7 intentos)");
            System.out.println("3. Dificil (1-100, 10 intentos)");
            int opcion = s.nextInt();

            int rango = 0;
            int intentosMax = 0;

            switch (opcion) {
                case 1:
                    rango = 10;
                    intentosMax = 5;
                    break;
                case 2:
                    rango = 50;
                    intentosMax = 7;
                    break;
                case 3:
                    rango = 100;
                    intentosMax = 10;
                    break;
                default:
                    System.out.println("Opcion no valida, se asignara nivel Medio por defecto.");
                    rango = 50;
                    intentosMax = 7;
            }

            // Generar el numero secreto en el rango seleccionado
            int numeroSecreto = ram.nextInt(rango) + 1;
            int intentosActuales = 0;
            boolean adivinado = false;

            // Bucle principal de intentos
            while (intentosActuales < intentosMax && !adivinado) {
                System.out.println("\nElige un numero entre 1 y " + rango + ": ");
                int numeroUsuario = s.nextInt();

                // Validacion: si esta fuera de rango no cuenta como intento
                if (numeroUsuario < 1 || numeroUsuario > rango) {
                    System.out.println("Numero fuera de rango, intenta de nuevo.");
                    continue;
                }

                intentosActuales++;

                if (numeroUsuario == numeroSecreto) {
                    adivinado = true;
                    System.out.println("\nFELICIDADES! Adivinaste el numero en " + intentosActuales + " intentos.");
                } else {
                    // Aqui se da la pista segun la comparacion
                    if (numeroUsuario < numeroSecreto) {
                        System.out.println("El numero secreto es MAS ALTO");
                    } else {
                        System.out.println("El numero secreto es MAS BAJO");
                    }
                    System.out.println("Te quedan " + (intentosMax - intentosActuales) + " intentos.");
                }
            }

            if (!adivinado) {
                System.out.println("\nHas perdido. El numero secreto era: " + numeroSecreto);
            }

            System.out.println("\nQuieres jugar de nuevo? (s/n)");
            String respuesta = s.next();

            if (!respuesta.equalsIgnoreCase("s")) {
                jugarDeNuevo = false;
                System.out.println("Gracias por jugar. Hasta la proxima!");
            }
        }

        s.close();
    }
}
