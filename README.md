# hello-world
Just another repository

Bueno esto es un pequeño intento en GitHub para 
entender un poco cómo funciona :)
-------------------
/*Comienzo la idea#1 =Juan Arce */
    package proyecto$ ;
/* Autores Grupo A */
    import java.util.Scanner;
    public class Banco {   
     public static void main(String[] args) {
        /* Se comienza el codigo base. Y se les desea una buena experiencia*/
        
        /*Clase01: Se aplica lo visto en determinada clase*/
        Scanner input = new Scanner(System.in);
        int op;
        
        String Cuenta;
        String Nombre;
        int Saldo_Inicial;
        String NIP;
                
        Cuenta obj= new Cuenta();
        
        do{    
        limpiar(10);
        System.out.println("*** MENU ***\n");
        System.out.println("1.- Crear Cuenta ");
        System.out.println("2.- Abonar ");
        System.out.println("3.- Retirar ");        
        System.out.println("4.- Consultar ");        
        System.out.println("5.- Salir ");
        
        /*Clase02: Se aplica lo visto en la Clase 2*/
        
        System.out.print("\nElija la Operacion que desea Realizar: ");        
        op = input.nextInt();
        input.nextLine(); 
        
        switch (op) {
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
                System.out.print("Ingrese el NIP:  ");
                NIP = input.nextLine();
                /*Se aplica la Variable NIP*/                                
                obj.Crear(Cuenta, Nombre, Saldo_Inicial, NIP);
                
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

                    if (obj.Validar(Cuenta, NIP)) {
                        System.out.print("Ingrese el monto a depositar: ");
                        int deposito = input.nextInt();
                        obj.Abonar(Cuenta, deposito);                                                  
                    }               
                    else
                        System.out.print("\nNúmero de cuenta y/o NIP incorrecto \n Vuelva a intentar \n");                    
                } while(obj.Validar(Cuenta, NIP)==false);
                input.nextLine();                
                input.nextLine();                
                break;
            case 3:
                do{                
                    System.out.print("Ingrese el numero de cuenta:  ");
                    Cuenta = input.nextLine();                
                    System.out.print("Ingrese el numero Secreto:  ");
                    NIP = input.nextLine();   

                    if (obj.Validar(Cuenta, NIP)) {
                        System.out.print("Ingrese el monto a retirar: ");
                        int retiro=input.nextInt();
                        obj.Retirar(Cuenta,retiro);                                                  
                    }               
                    else
                        System.out.print("\nNúmero de cuenta y/o NIP incorrecto \nVuelva a intentarlo \n");                    
                } while(obj.Validar(Cuenta, NIP)==false);                      
                input.nextLine();                
                input.nextLine();
                break;
                
            case 4://Consultar
                do{
                System.out.print("Ingrese el numero de cuenta:  ");
                Cuenta = input.nextLine();                
                System.out.print("Ingrese el numero Secreto:  ");
                NIP = input.nextLine();
                
                if (obj.Validar(Cuenta, NIP)) {                                  
                    obj.Consultar(Cuenta);
                    input.nextLine();
                } else
                    System.out.print("Número de cuenta y/o NIP incorrecto \nVuelva a intentarlo \n");                    
                }while(obj.Validar(Cuenta, NIP)==false);
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

