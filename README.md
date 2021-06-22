# hello-world
Just another repository

Bueno esto es un pequeño intento en GitHub para 
entender un poco cómo funciona :)
---------------------------------------
/*Comienzo la idea#1 =Juan Arce */
    package proyecto$ ;
/* Autores Grupo A */
    import java.util.Scanner;
    public class Banco {   
     public static void main(String[] args) {
        /* Se comienza el codigo base. Y se les desea una buena experiencia*/
        
        /*Clase01: Se aplica lo visto en determinada clase*/       [Se aplica Scanner(System.in)]
        Scanner input = new Scanner(System.in);                    [
        int op;                                                    [
        
        String Cuenta;                                             [Variable 1]
        String Nombre;                                             [Variable 2]
        int Saldo_Inicial;                                         [Variable 3]
        String PIN;                                                [Variable 4]
                
        Cuenta obj= new Cuenta();
        
        do{                                                        [Se aplica dp{ para: por ejecutar un menu de opciones]
        limpiar(10);
        System.out.println("*** MENU ***\n");
        System.out.println("1.- Crear Cuenta ");                   [Opcion 1]
        System.out.println("2.- Abonar ");                         [Opcion 2]
        System.out.println("3.- Retirar ");                        [Opcion 3]
        System.out.println("4.- Consultar ");                      [Opcion 4]
        System.out.println("5.- Salir ");                          [Opcion 5]
        
        /*Clase02: Se aplica lo visto en la Clase 2*/
        
        System.out.print("\nElija la Operacion que desea Realizar: ");        
        op = input.nextInt();
        input.nextLine(); 
        
        switch (op) {                                   [Caso 1: El usuario no posee cuenta y quiere crear una]
            case 1:                
                System.out.print("Ingrese el Número de cuenta a Crear:  ");
                Cuenta = input.nextLine();
                /*Se aplica la variable Cuenta*/
                System.out.print("Ingrese el Nombre del Titular:  ");
                Nombre = input.nextLine();
                /*Se aplica la variable Nombre*/
                System.out.print("Ingrese el Saldo Inicial:  ");
                Saldo_Inicial = input.nextInt();
                /*Se aplica el Saldo Inicial*/
                input.nextLine();//Limpiar el buffer 
                System.out.print("Ingrese el PIN:  ");
                NIP = input.nextLine();
                /*Se aplica la Variable PIN*/                                
                obj.Crear(Cuenta, Nombre, Saldo_Inicial, PIN);
                
        /*Clase03: Se apica lo visto en la Clase 3.*/ 
        /*Se impletara if/else/while*/
                
                input.nextLine();
                break;
            case 2:
                do{                
                    System.out.print("Ingrese el número de cuenta:  ");
                    Cuenta = input.nextLine();                
                    System.out.print(" Ingrese el numero Secreto:  ");
                    NIP = input.nextLine();   

                    if (obj.Validar(Cuenta, PIN)) {
                        System.out.print("Ingrese el monto a depositar: ");
                        int deposito = input.nextInt();
                        obj.Abonar(Cuenta, deposito);                                                  
                    }               
                    else
                        System.out.print("\nNúmero de cuenta y/o NIP incorrecto \n Vuelva a intentar \n");                    
                } while(obj.Validar(Cuenta, PIN)==false);
                input.nextLine();                
                input.nextLine();                
                break;
            case 3:
                do{                
                    System.out.print("Ingrese el numero de cuenta:  ");
                    Cuenta = input.nextLine();                
                    System.out.print("Ingrese el numero Secreto:  ");
                    NIP = input.nextLine();   

                    if (obj.Validar(Cuenta, PIN)) {
                        System.out.print("Ingrese el monto a retirar: ");
                        int retiro=input.nextInt();
                        obj.Retirar(Cuenta,retiro);                                                  
                    }               
                    else
                        System.out.print("\nNúmero de cuenta y/o PIN incorrecto \nVuelva a intentarlo \n");                    
                } while(obj.Validar(Cuenta, PIN)==false);                      
                input.nextLine();                
                input.nextLine();
                break;
                
            case 4://Consultar
                do{
                System.out.print("Ingrese el numero de cuenta:  ");
                Cuenta = input.nextLine();                
                System.out.print("Ingrese el numero Secreto:  ");
                NIP = input.nextLine();
                
                if (obj.Validar(Cuenta, PIN)) {                                  
                    obj.Consultar(Cuenta);
                    input.nextLine();
                } else
                    System.out.print("Número de cuenta y/o PIN incorrecto \nVuelva a intentarlo \n");                    
                }while(obj.Validar(Cuenta, PIN)==false);
                break;
                
            case 5:                
                System.out.println("\n\nGracias por utilizar ATM'S Service \n Presione una tecla para continuar");  
                input.nextLine();
                System.exit(0);
                break;
            default:               
                break;
            }              
        }while (op!=5);  
    }

    public static void limpiar(int lineas)
    {
        for (int i=0; i < lineas; i++)
            {
                System.out.println();
            }
    }
    
}

